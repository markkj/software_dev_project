# API DOCS 

## LIST OF API 

- User 
    - Information
    - Registered
    - Unregistered
- Course 
    - Information
    - Course Available
- Curriculum 
    - Information
    - List Subjects
- Faculty
  - Information 
- Major 
  - Information 
- Section 
  - Information

# User 
## Information
### ENDPOINT       
    GET https://secure-reef-62579.herokuapp.com/student/60010105
### Prerequisite 
    - None 
### Request :  
    - None
### Response:  
    {
        "student_id": "60010105",
        "name": "Khajohnyos Boonkate",
        "email": "60010105@kmitl.ac.th",
        "student_year": "4",
        "department_id": "Computer Engineering",
        "major_id": "Information Engineering",
        "faculty_id": "Engineering"
    }
## Registered
### ENDPOINT
    GET https://secure-reef-62579.herokuapp.com/student/registered/60010105
### Prerequisite 
    - None 
### Request :  
    - None
### Response:  
    [
        {
            "id": 1,
            "year": "1",
            "semester": "1",
            "student_id": "60010105",
            "student": {
                "student_id": "60010105",
                "name": "Khajohnyos Boonkate",
                "email": "60010105@kmitl.ac.th",
                "student_year": "4",
                "department_id": "Computer Engineering",
                "major_id": "Information Engineering",
                "faculty_id": "Engineering"
            },
            "courses": [
                {
                    "id": 1,
                    "section": "1",
                    "grade": 4,
                    "course_id": "01006028",
                    "course": {
                        "course_id": "01006028",
                        "title": "PRE-ACTIVITIES FOR ENGINEERS",
                        "credit": 1,
                        "description": "Participates in activities organized by the Faculty of Engineering of advising and preparing students for succcessful Engineering education and career. Fundamental Laboratory and project in science and technology. ",
                        "category_id": "02",
                        "group_id": "07",
                        "type": "Credit",
                        "prerequisite": "None",
                        "status": "true",
                        "section": null
                    }
                },...]
        },...
        
    ]
## Unregistered
### ENDPOINT
    GET https://secure-reef-62579.herokuapp.com/student/unregistered/60010105
### Prerequisite 
    - None 
### Request :  
    - None
### Response:  
    [
        {
            "course_id": "01236028",
            "title": "PROJECT 2",
            "credit": 3,
            "description": "Participates in activities organized by the Faculty of Engineering of advising and preparing students for succcessful Engineering education and career. Fundamental Laboratory and project in science and technology. ",
            "category_id": "02",
            "group_id": "08",
            "type": "Credit",
            "prerequisite": "01236027",
            "status": "true",
            "section": null
        },
        ....
    ]
# Course (รายวิชา) 
## Information
### ENDPOINT    
    GET : https://secure-reef-62579.herokuapp.com/courses/{course_id}
### Prerequisite 
    - None 
### Request :  
    - None
### Response:  
    {
        "course_id": "01236152",
        "title": "SELECTED TOPICS IN SOFTWARE DEVELOPMENT",
        "credit": 3,
        "description": "Participates in activities organized by the Faculty of Engineering of advising and preparing students for succcessful Engineering education and career. Fundamental Laboratory and project in science and technology. ",
        "category_id": "02",
        "group_id": "10",
        "type": "Credit",
        "prerequisite": "none",
        "status": "true",
        "section": null
    } 
## Course Available
### ENDPOINT       
    Use https://secure-reef-62579.herokuapp.com/student/unregistered/60010105
    GET https://secure-reef-62579.herokuapp.com/student/unregistered/60010105
### Prerequisite 
  - None 
### Request :  
    { 
        " Student_ID ": "60010105", 
    } 
### Response:  
    { 
        "subjects":[
            {
                "year":"4",
                "semester:"2",
                "subjects:[]
            }
        ]
    }

## Information
### ENDPOINT       
    GET : /Major/{Major_ID}/ 
### Prerequisite 
  - None 
### Request :  
    { 
        "Major_ID": "01", 
    } 
### Response:  
    { 
        "ID":"02", 
        "Title":"Information Engineering" 
    } 

 
# Credit Checking (ดูจำนวนหน่วยกิตที่เหลือ)
## Information
### ENDPOINT
    GET : https://secure-reef-62579.herokuapp.com/student/check/60010105
### Prerequisite 
### Request :  
### Response:  
    {
        "Credit":{
            "Curriculum_credit":"138",
            "Presemester_credit":"120",
            "Registed_credit":"7",
            "Target_credit":"127",
            "Needed_credit":"11"
        },
        "structure":{ 
            "specific":{ 
                "กลุ่มวิชาเลือกเฉพาะสาขา":"3" 
            }, 
            "free":"6" 
        } 
    }


## LIST OF CLASS (For Spring-Boot Service)
    - Course
    - Curriculum
    - CourseOfCurriculum
    - Major
    - Faculty
    - Group
    - Category
    - Credit

## HOST URL

    https://shielded-brook-09988.herokuapp.com/api/
 

# Result Sample

# Course
## Get All Courses
### END POINT
    GET : https://shielded-brook-09988.herokuapp.com/api/Course
### Prerequisite 
      - None 
### Request :
      - None
### Response :

        [
            {

                "code_id": "01006004",
                "title_th": "การฝึกงานอุตสาหกรรม",
                "title_en": "INDUSTRIAL TRAINING",
                "credit": 0,
                "credit_struct": "(0-45-0)",
                "description_th": "เป็นการฝึกงานภาคปฎิบัติที่จัดขึ้นตามสาขาวิชา โดยการฝึกงานในโรงงานอุตสาหกรรม หรือ บริษัทเอกชน ทั้งในประเทศและต่างประเทศ ทั้งนี้เพื่อเป็นการเสริมสร้างประสบการณ์นักศึกษาทุกคน 
                จะต้องผ่านการฝึกงานในช่วงของการศึกษาฤดูร้อน พร้อมทั้งเขียนรายงานเสนอ",
                "description_en": "During their four-year selected studies, students are required to complete a short term industrial placement within professional selected environments. It takes place during a summer period. This course allows students to put into practice under conditions reflecting their future activities and reponsesibilities. The work, carried out under the responsibility of the firm involved, is presented in a written report.",
                "type": "Credit",
                "category_ID": 2,
                "c_group_ID": 7,
                "prerequisite": "None",
                "prerequisite_ID": 0,
                "id": 1006004
            },
            {
                "code_id": "01006028",
                "title_th": "เตรียมความพร้อมสําหรับวิศวกร",
                "title_en": "PRE-ACTIVITIES FOR ENGINEERS",
                "credit": 1,
                "credit_struct": "(0-3-2)",
                "description_th": "การเข้าร่วมกิจกรรมทางคณะวิศวกรรมศาสตร์จัดเตรียมขึ้น เพื่อเป็นการแนะแนว และเตรียม ความพร้อมนักศึกษาในการศึกษาและประกอบอาชีพวิศวกรที่ประสบความสําเร็จ ปฏิบัติการพื้นฐานและ โครงงานเบื้องต้นทางวิทยาศาสตร์และเทคโนโลยี",
                "description_en": "Participates in activities organized by the Faculty of Engineering of advising and preparing students for successful engineering education and career. Fundamental laboratory and project in science and technology.",
                "type": "Credit",
                "category_ID": 2,
                "c_group_ID": 7,
                "prerequisite": "None",
                "prerequisite_ID": 0,
                "id": 1006028
            },
            {
                "code_id": "01006030",
                "title_th": "แคลคูลัส 1",
                "title_en": "CALCULUS 1",
                "credit": 3,
                "credit_struct": "(3-0-6)",
                "description_th": "ฟังก์ชัน ลิมิต ความต่อเนื่อง และการประยุกต์ใช้อุปนัยเชิงคณิตศาสตร์แนะนําอนุพันธ์การหา อนุพันธ์การประยุกต์ใช้อนุพันธ์ปริพันธ์จํากัดเขต การปริพันธ์ด้วยปฏิยานุพันธ์การประยุกต์ใช้ปริพันธ์ จํากัดเขต รูปแบบของการปริพันธ์ที่หาค่าไม่ได้ปริพันธ์ไม่ตรงแบบ การหาปริพันธ์ด้วยวิธีเชิงตัวเลข อันดับ และอนุกรมของจํานวน การกระจายอนุกรมเทเลอร์ของฟังก์ชันพื้นฐาน การวิเคราะห์เวกเตอร์",
                "description_en": "Function, Limit, Continuity and their applications, Mathematical induction, Introduction to derivative, Differentiation, Applications of derivative, Definite integrals,Antiderivative integration, Application of definite integral, Indeterminate forms, Improper integrals, Numerical integration, Sequences and series of numbers, Taylor series expansions of elementary functions, Vector analysis.",
                "type": "Credit",
                "category_ID": 2,
                "c_group_ID": 7,
                "prerequisite": "None",
                "prerequisite_ID": 0,
                "id": 1006030
            },
            {
                "code_id": "01006031",
                "title_th": "แคลคูลัส 2",
                "title_en": "CALCULUS 2",
                "credit": 3,
                "credit_struct": "(3-0-6)",
                "description_th": "ฟังก์ชันหลายตัวแปรและการประยุกต์ใช้พีชคณิตของเวกเตอร์ในสามมิติพิกัดเชิงขั้ว แคลคูลัสของ ฟังก์ชันจํานวนจริงสองตัวแปร การหาอนุพันธ์และปริพันธ์ของฟังก์ชันจํานวนจริงและฟังก์ชันเวกเตอร์ จํานวนจริงหลายตัวแปร แนะนําปรพิ ันธ์เส้น เส้น ระนาบ และพื้นผิว ในปริภูมิสามมิติแคลคูลัสของฟังก์ชัน จํานวนจริงในปริภูมิสามมิติทฤษฎีบทหลักที่เกี่ยวกับการประยุกต์เช่น ทฤษฎีบทของกรีน ทฤษฎีไดเวอร์ เจนซ์ทฤษฎีบทของเกาส์ทฤษฎีบทของสโตกส์เป็นต้น",
                "description_en": "Functions of several variables and theirs applications,Vector algebra in three dimensions,Polar coordinates,Calculus of real - valued functions of two variables,Differentiation and integration of real - valued and vector - valued functions of multiple real variables.",
                "type": "Credit",
                "category_ID": 2,
                "c_group_ID": 7,
                "prerequisite": "01006030 CALCULUS 1",
                "prerequisite_ID": 1006030,
                "id": 1006031

            }
        ]

# Curriculum
## Get All Curriculums
### END POINT
    GET : https://shielded-brook-09988.herokuapp.com/api/Curriculum
### Prerequisite 
      - None 
### Request :
      - None
### Response :

        [
            {
                "code_id": "25520161105552",
                "title_thai": "หลักสูตรวิศวกรรมศาสตรบัณฑิต สาขาวิศวกรรมสารสนเทศ",
                "title_eng": "Bachelor of Engineering Program in Information Engineering",
                "degree_title_full_th": "วิศวกรรมศาสตรบัณฑิต (วิศวกรรมสารสนเทศ)",
                "degree_title_full_en": "Bachelor of Engineering (Information Engineering)",
                "degree_title_short_th": "วศ.บ. (วิศวกรรมสารสนเทศ)",
                "degree_title_short_en": "B.Eng (Information Engineering)",
                "revision": "2560",
                "faculty_ID": 1,
                "major_ID": 1,
                "student_year": 4,
                "program_type": "หลักสูตรปริญญาตรีทางวิชาการ",
                "program_language": "หลักสูตรการศึกษาภาษาไทย/ภาษาอังกฤษ",
                "program_in_condition": "รับทั้งนักศึกษาไทยและนักศึกษาต่างชาติที่ใช้ภาษาไทยได้ดี",
                "program_out_condition": "ให้ปริญญาเพียงสาขาวิชาเดียว",
                "id": 25520161105552,
                "mou": "หลักสูตรวสถาบันโดยเฉพาะ"
            }
        ]


## Get a  Curriculum
### END POINT
    GET : https://shielded-brook-09988.herokuapp.com/api/Curriculum/{curriculum_id}
### Prerequisite 
      - None 
### Request :
    {
        "id": 25520161105552
    }
### Response :

    {
        "code_id": "25520161105552",
        "title_thai": "หลักสูตรวิศวกรรมศาสตรบัณฑิต สาขาวิศวกรรมสารสนเทศ",
        "title_eng": "Bachelor of Engineering Program in Information Engineering",
        "degree_title_full_th": "วิศวกรรมศาสตรบัณฑิต (วิศวกรรมสารสนเทศ)",
        "degree_title_full_en": "Bachelor of Engineering (Information Engineering)",
        "degree_title_short_th": "วศ.บ. (วิศวกรรมสารสนเทศ)",
        "degree_title_short_en": "B.Eng (Information Engineering)",
        "revision": "2560",
        "faculty_ID": 1,
        "major_ID": 1,
        "student_year": 4,
        "program_type": "หลักสูตรปริญญาตรีทางวิชาการ",
        "program_language": "หลักสูตรการศึกษาภาษาไทย/ภาษาอังกฤษ",
        "program_in_condition": "รับทั้งนักศึกษาไทยและนักศึกษาต่างชาติที่ใช้ภาษาไทยได้ดี",
        "program_out_condition": "ให้ปริญญาเพียงสาขาวิชาเดียว",
        "id": 25520161105552,
        "mou": "หลักสูตรวสถาบันโดยเฉพาะ"
    }

## Get a Information of Curriculum
### END POINT
    GET : https://shielded-brook-09988.herokuapp.com/api/Curriculum/info/{curriculum_id}
### Prerequisite 
      - None 
### Request :
    {
        "id": 25520161105552
    }
### Response :

    {
        "Faculty_ID": 1,
        "Structure_Curriculum": {
            "total_credit": 138,
            "Structure": {
                "free": 6,
                "specific": {
                    "กลุ่มวิชาวิศวกรรมพื้นฐาน": 20,
                    "กลุ่มเลือกวิชาเฉพาะสาขา": 12,
                    "กลุ่มวิชาวิศวกรรมสารสนเทศพื้นฐาน": 64,
                    "กลุ่มวิชาการศึกษาทางเลือก": 6
                },
                "genend": {
                    "กลุ่มวิชาคุณค่าแห่งชีวิต": 6,
                    "กลุ่มวิชาภาษาและการสื่อสาร": 12,
                    "กลุ่มวิชาศิลปะแห่งการจัดการ": 3,
                    "กลุ่มวิชาวิถีแห่งสัมคม": 3,
                    "วิชาเลือก(เลือกทั้ง 5 กลุ่ม)": 3,
                    "กลุ่มวิชาคุณค่าแห่งความคิด": 3
                }
            }
        },
        "Revision": "2560",
        "Program_Type": {
            "out_condition": "ให้ปริญญาเพียงสาขาวิชาเดียว",
            "MOU": "หลักสูตรวสถาบันโดยเฉพาะ",
            "languages": "หลักสูตรการศึกษาภาษาไทย/ภาษาอังกฤษ",
            "type": "หลักสูตรปริญญาตรีทางวิชาการ",
            "Study_Years": 4,
            "in_condition": "รับทั้งนักศึกษาไทยและนักศึกษาต่างชาติที่ใช้ภาษาไทยได้ดี"
        },
        "Title": {
            "thai": "หลักสูตรวิศวกรรมศาสตรบัณฑิต สาขาวิศวกรรมสารสนเทศ",
            "eng": "Bachelor of Engineering Program in Information Engineering"
        },
        "ID": "25520161105552",
        "Degree_Title": {
            "full_name": {
                "thai": "วิศวกรรมศาสตรบัณฑิต (วิศวกรรมสารสนเทศ)",
                "eng": "Bachelor of Engineering (Information Engineering)"
            },
            "short_name": {
                "thai": "วศ.บ. (วิศวกรรมสารสนเทศ)",
                "eng": "B.Eng (Information Engineering)"
            }
        }
    }


# CourseOfCurriculum
## Get All CoursesOfCurriculum
### END POINT
    GET : https://shielded-brook-09988.herokuapp.com/api/CourseOfCurriculum
### Prerequisite 
      - None 
### Request :
      - None
### Response :

    [
        {
            "recommend_semester": "3/3",
            "minimum_year": 3,
            "id": "9c5e319c-0b79-4a4d-94bb-03b6b414d199",
            "course_id": 1006004,
            "curriculum_id": 25520161105552
        },
        {
            "recommend_semester": "1/1",
            "minimum_year": 1,
            "id": "5dc0c6e1-77fc-4a13-9459-b1516b4d16ca",
            "course_id": 1006028,
            "curriculum_id": 25520161105552
        },
        {
            "recommend_semester": "1/1",
            "minimum_year": 1,
            "id": "821135b3-99ff-40d1-b6de-43217c694805",
            "course_id": 1006030,
            "curriculum_id": 25520161105552
        }
    ]


# Major
## Get All Majors
### END POINT
    GET : https://shielded-brook-09988.herokuapp.com/api/Major
### Prerequisite 
      - None 
### Request :
      - None
### Response :

    [
        {
            "title": "วิศวกรรมคอมพิวเตอร์",
            "faculty_ID": 1,
            "id": 1
        }
    ]


# Faculty
## Get All Faculties
### END POINT
    GET : https://shielded-brook-09988.herokuapp.com/api/Faculty
### Prerequisite 
      - None 
### Request :
      - None
### Response :

    [
        {
            "title": "วิศวกรรมศาสตร์",
            "id": 1
        }
    ]


# Group
## Get All Courses
### END POINT
    GET : https://shielded-brook-09988.herokuapp.com/api/Group
### Prerequisite 
      - None 
### Request :
      - None
### Response :

    [
        {
            "title": "กลุ่มวิชาคุณค่าแห่งชีวิต",
            "category_ID": 1,
            "id": 1
        },
        {
            "title": "กลุ่มวิชาคุณค่าแห่งความคิด",
            "category_ID": 1,
            "id": 3
        },
        {
            "title": "กลุ่มวิชาวิถีแห่งสัมคม",
            "category_ID": 1,
            "id": 2
        },
        {
            "title": "กลุ่มวิชาศิลปะแห่งการจัดการ",
            "category_ID": 1,
            "id": 4
        },
        {
            "title": "กลุ่มวิชาภาษาและการสื่อสาร",
            "category_ID": 1,
            "id": 5
        },
        {
            "title": "วิชาเลือก(เลือกทั้ง 5 กลุ่ม)",
            "category_ID": 1,
            "id": 6
        },
        {
            "title": "กลุ่มวิชาวิศวกรรมพื้นฐาน",
            "category_ID": 2,
            "id": 7
        },
        {
            "title": "กลุ่มวิชาวิศวกรรมสารสนเทศพื้นฐาน",
            "category_ID": 2,
            "id": 8
        },
        {
            "title": "กลุ่มวิชาการศึกษาทางเลือก",
            "category_ID": 2,
            "id": 9
        },
        {
            "title": "กลุ่มเลือกวิชาเฉพาะสาขา",
            "category_ID": 2,
            "id": 10
        },
        {
            "title": "free",
            "category_ID": 3,
            "id": 11
        }
    ]


# Category
## Get All Categories
### END POINT
    GET : https://shielded-brook-09988.herokuapp.com/api/Category
### Prerequisite 
      - None 
### Request :
      - None
### Response :

    [
        {
            "title": "หมวดวิชาศึกษาทั่วไป",
            "id": 1
        },
        {
            "title": "หมวดวิชาเฉพาะ",
            "id": 2
        },
        {
            "title": "หมวดวิชาเลือกเสรี",
            "id": 3
        }
    ]


# Credit
## Get All Credits
### END POINT
    GET : https://shielded-brook-09988.herokuapp.com/api/Credit
### Prerequisite 
      - None 
### Request :
      - None
### Response : 

    [
        {
            "category_ID": 1,
            "c_group_ID": 1,
            "credit_amount": 6,
            "curriculum_ID": 25520161105552,
            "id": "8807eb89-c62e-412e-b4c6-bf972567f27c"
        },
        {
            "category_ID": 1,
            "c_group_ID": 2,
            "credit_amount": 3,
            "curriculum_ID": 25520161105552,
            "id": "44730c39-aad7-44f4-aec9-481547a81892"
        },
        {
            "category_ID": 1,
            "c_group_ID": 3,
            "credit_amount": 3,
            "curriculum_ID": 25520161105552,
            "id": "c09e355e-9e00-4200-84e2-3f97fb923bfa"
        },
        {
            "category_ID": 1,
            "c_group_ID": 4,
            "credit_amount": 3,
            "curriculum_ID": 25520161105552,
            "id": "fe5deab2-d8c8-4b55-bdd9-43f481a1649b"
        },
        {
            "category_ID": 1,
            "c_group_ID": 5,
            "credit_amount": 12,
            "curriculum_ID": 25520161105552,
            "id": "e25e6b67-d206-45af-9b6f-2e487ed01437"
        },
        {
            "category_ID": 1,
            "c_group_ID": 6,
            "credit_amount": 3,
            "curriculum_ID": 25520161105552,
            "id": "692fbcea-1333-4163-b04d-1a0c952d9ff8"
        },
        {
            "category_ID": 2,
            "c_group_ID": 7,
            "credit_amount": 20,
            "curriculum_ID": 25520161105552,
            "id": "0422f166-f32b-4975-806c-2252478880eb"
        },
        {
            "category_ID": 2,
            "c_group_ID": 8,
            "credit_amount": 64,
            "curriculum_ID": 25520161105552,
            "id": "92a5b3c5-f637-40f8-89f8-451b644a21b9"
        },
        {
            "category_ID": 2,
            "c_group_ID": 9,
            "credit_amount": 6,
            "curriculum_ID": 25520161105552,
            "id": "d64f8dc0-0131-4e4c-976b-ee489c920ee5"
        },
        {
            "category_ID": 2,
            "c_group_ID": 10,
            "credit_amount": 12,
            "curriculum_ID": 25520161105552,
            "id": "d902124e-3cd7-4f07-a9c0-b604df18627e"
        },
        {
            "category_ID": 3,
            "c_group_ID": 11,
            "credit_amount": 6,
            "curriculum_ID": 25520161105552,
            "id": "51aef98d-a315-41de-978b-cd5b86d4667e"
        }
    ]
