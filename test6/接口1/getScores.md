# 接口：getScores  [返回](../README.md)
用例： [查看成绩列表](../用例1/查看成绩列表.md)

- 功能：
   根据课程编号及学号返回成绩列表。
    
- 权限：
    学生/老师。    
    
- API请求地址： 
    接口基本地址/v1/api/getScores

- 请求方式：
    POST

- 请求实例：

        {
            "course_id": "11112",
            "student_id": "201510414202"
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程编号，对应唯一课程|
  |student_id|学号，对应唯一学生|
  
  
- 返回实例：

        { 
            "status": true,
            "info": null,
            "data": {
                "course_id": "11112"
                "student_id": "201510414202"
                "web_sum": 1
                "update_date": null
                "grades": [{
                    "tests_id": 1
                    "tests_score": 100,
                    "tests_comment": "完成程度较好",
                    "tests_update_date": "2018-6-1 12:0:0"
                    "tests_web_sum": 0
                }
                "grades": [{
                    "tests_id": 2
                    "tests_score": 100,
                    "tests_comment": "完成程度很好",
                    "tests_update_date": "2018-6-1 12:10:0"
                    "tests_web_sum": 0
                }
                ......
                ]
            }    
        }

- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |data|返回主体信息JSON串|
  |tests|返回课程对应的所有实验集合，若空则返回[]|
  |course_id|课程编号|
  |student_id|学号|
  |tests_score|课程成绩|
  |tests_comment|课程评价|
  |tests_web_sum|学生课程GitHub地址是否正确，1正确，0错误|
  |tests_update_date|课程成绩批改时间|
  |grades|实验成绩集合|
  |update_date|用户GitHub账号修改日期|

