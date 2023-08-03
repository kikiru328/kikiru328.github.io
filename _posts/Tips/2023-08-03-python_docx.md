---
title : "Python를 이용한 반복작업 words 자동화 코드"
excerpt : "Python - docx"

categories: 
 - Tips
tags:  
 - [Python, docx, words, table]


toc : true
toc_sticky : true



date : 2023-08-03
last_modified_dat : 2023-08-03
---
<div class='notice--info' markdown='1'>
python-docx를 이용해서 워드 작업을 해보자
</div>

<div class='notice--danger' markdown='1'>

가끔 행정일을 하다보면, 동일한 `layout`에 여러 작업을 하는  
`여간 귀찮은 일`이 많다.  

그래서 `python-docx`를 이용해서 반복작업을 자동화해보자.
</div>

```python
from docx import Document
import copy
import pandas as pd
import os
import docx as doc
import pandas as pd
import argparse
parser = argparse.ArgumentParser()
parser.add_argument('--format', type=str, default='./format.docx')
parser.add_argument('--data', type=str, default='./test_df.xlsx')
parser.add_argument('--save', type=str, default='./test.docx')
args = parser.parse_args()

"""
python share_auto.py --format='format.docx' --data='input_data.xlsx' --save='save_path'
"""

def cell_info(table):
    cell_locations = {
                'FIX' : 
                    {
                        'title' : table.rows[0].cells[0].text,
                        'object' : table.rows[1].cells[0].text,
                        'processing' : table.rows[2].cells[0].text,
                        'issue' : table.rows[5].cells[0].text,
                        'revise' : table.rows[9].cells[0].text,
                        'writer' : table.rows[13].cells[0].text,
                        'checker' : table.rows[13].cells[2].text,
                        'write_date' : table.rows[15].cells[0].text,
                        'chck_date' : table.rows[14].cells[2].text
                    }
                ,
                'VAR' : {
                    'title_text' :  table.rows[0].cells[1],
                    'object_text' : table.rows[1].cells[1],
                    'processing_text' : table.rows[3].cells[0],
                    'processing_text_detail': table.rows[4].cells[0],
                    'issue_roi_image' : table.rows[6].cells[0].paragraphs[0],
                    'issue_raw_image': table.rows[6].cells[2].paragraphs[0],
                    'issue_image_explain' : table.rows[7].cells[0],
                    'issue_content' : table.rows[8].cells[0],
                    'revise_image' : table.rows[10].cells[0].paragraphs[0],
                    'revise_image_explain' : table.rows[11].cells[0],
                    'revise_content' : table.rows[12].cells[0],
                    'writer' : table.rows[14].cells[1],
                    'writing_date' : table.rows[16].cells[1]
                }
            }        
    return cell_locations


def add_new_page_with_table(document, format_table):
    # Add a new paragraph with a page break
    paragraph = document.add_paragraph()
    run = paragraph.add_run()
    run.add_break(doc.enum.text.WD_BREAK.PAGE)

    # Create a copy of the format_table
    new_table = copy.deepcopy(format_table)

    # Append the copied table to the new paragraph
    paragraph._element.append(new_table._tbl)

    return new_table  # Return the newly added table

def update_row_cells(table_instance, data_table, ind):
    df = data_table.copy()
    # Update the cells in the row with new content
    cell_locations = cell_info(table_instance)
    
    cell_locations['VAR']['title_text'].text = df.title_text[ind]
    cell_locations['VAR']['object_text'].text = df.object_text[ind]
    
    cell_locations['VAR']['processing_text'].text = df.processing_text[ind]
    cell_locations['VAR']['processing_text_detail'].text = df.processing_text_detail[ind]

    i_roi_p = cell_locations['VAR']['issue_roi_image'].add_run()
    i_roi_p.add_picture(df.issue_roi_image[ind], width=doc.shared.Cm(8), height = doc.shared.Cm(5))

    i_raw_p = cell_locations['VAR']['issue_raw_image'].add_run()
    i_raw_p.add_picture(df.issue_raw_image[ind], width=doc.shared.Cm(8), height = doc.shared.Cm(5))

    cell_locations['VAR']['issue_image_explain'].text = df.issue_image_explain[ind]
    issue_explain_para = cell_locations['VAR']['issue_image_explain'].paragraphs[0]
    issue_explain_para.alignment = doc.enum.text.WD_ALIGN_PARAGRAPH.CENTER

    cell_locations['VAR']['issue_content'].text = df.issue_content[ind]

    i_revise_p = cell_locations['VAR']['revise_image'].add_run()
    i_revise_p.add_picture(df.revise_image[ind], width=doc.shared.Cm(10), height = doc.shared.Cm(7))

    cell_locations['VAR']['revise_image_explain'].text = df.revise_image_explain[ind]
    revise_image_explain = cell_locations['VAR']['revise_image_explain'].paragraphs[0]
    revise_image_explain.alignment = doc.enum.text.WD_ALIGN_PARAGRAPH.CENTER

    cell_locations['VAR']['revise_content'].text = df.revise_content[ind]

    cell_locations['VAR']['writer'].text = df.writer[ind]
    cell_locations['VAR']['writing_date'].text = df.writing_date[ind]

    writer_para = cell_locations['VAR']['writer'].paragraphs[0]
    date_para = cell_locations['VAR']['writing_date'].paragraphs[0]
    writer_para.alignment = doc.enum.text.WD_ALIGN_PARAGRAPH.CENTER
    date_para.alignment = doc.enum.text.WD_ALIGN_PARAGRAPH.CENTER



if __name__ == '__main__':
    document = Document(args.format)
    format_table = document.tables[0]  # Adjust the index as needed

    analysis_table = pd.read_excel(args.data)

    # Number of new pages to add
    table_instances = [format_table]

    for i in range(1, len(analysis_table)):
        format_table = add_new_page_with_table(document, format_table)
        table_instances.append(format_table)

    # # Update
    for ind, table_instance in enumerate(table_instances):
        data_table = analysis_table.iloc[[ind]]
        update_row_cells(table_instance, data_table, ind)

    document.save(args.save)

```

샘플 layout은 git에 첨부해두었으니 참고하시면 됩니다.


```
✏️ 개인 공부 기록용 블로그입니다! 틀린 부분이 있으면 언제든지 댓글로 알려주세요!
👍 항상 감사합니다!
```
