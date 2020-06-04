โค้ด gs
--------------------_----------__----
function doGet(request) {
  return HtmlService.createTemplateFromFile('index')
      .evaluate();
}

function include(filename) {
  return HtmlService.createHtmlOutputFromFile(filename)
      .getContent();
}

function processForm(formObject) {
  var url = "https://docs.google.com/spreadsheets/d/1td9wCTpMkLKPYEr7nBz0ho1td8uarujM_u1km8RsYpE/edit#gid=0";
  var ss = SpreadsheetApp.openByUrl(url);
  var ws = ss.getSheetByName("แผ่น1");
  ws.appendRow([formObject.gender, //เพศ
                formObject.age, //อายุ
                formObject.plan, //ระดับชั้น
                formObject.hobby, //ข้อ 1
                formObject.hobby1,
                formObject.hobby2,
                formObject.hobby3
               ]);
  }
  --------------------------------------------------
  โค้ด index
 --------------------------------------------------
<!DOCTYPE html>
<html>
    <head>
        <base target="_top">
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" 
        integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
           <link href='https://fonts.googleapis.com/css?family=Prompt' rel='stylesheet' type='text/css'>
        <style type='text/css'>
        @font-face {
        font-family: 'Prompt';
        }body { font-family: 'Prompt' !important; }

::placeholder {
  color: peachpuff;
  font-size: 14px;
  text-align: left; 
}

</style>
        <?!= include('JavaScript'); ?>
    </head>
    <body>
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <form id="myForm" onsubmit="handleFormSubmit(this)">
                    
                        <img src="url ของรูปภาพหัวเว็บ รร" width="100%" class="img-fluid" alt="Responsive image">
                        <div class="alert alert-primary"  role="alert"><center>
                        <B><font size=4>ระบบการรับสมัครนักเรียน ประจำปีการศึกษา 2563</font></B>
                        </center></div>
                        
                        <div class="alert alert-success" role="alert">
                        <h6 class="font-weight-bold">แบบสำรวจความเห็น</h6>
                        <p>การสำรวจครั้งนี้จัดทำโดยสภาเด็กและเยาวชนแห่งประเทศไทย  สถาบันยุวทัศน์แห่งประเทศไทย  
                        สมาคมผู้บำเพ็ญประโยชน์แห่งประเทศไทยในพระบรมราชินูปถัมภ์  สมาคมไอเซคพัฒนาผู้นำนักศึกษาระหว่างประเทศ  
                        เครือข่ายเด็กรุ่นใหม่ไม่พนัน และเครือข่ายเพื่อนเยาวชนเพื่อการพัฒนา   
                        มีวัตถุประสงค์เพื่อสำรวจความคิดเห็นและประสบการณ์ตรงในการใช้สื่อออนไลน์ของเพื่อนเยาวชน
                        ในสถานการณ์การล็อคดาวน์อยู่กับบ้านจากการแพร่ระบาดของเชื้อไวรัสโควิด19   
                        คำตอบของเพื่อนทุกคนจะถูกนำไปประมวลผลในภาพรวม โดยไม่เกี่ยวโยงใด ๆ ต่อผู้ตอบ  
                        จึงขอให้เพื่อน ๆ ตอบข้อคำถามต่อไปนี้ตามความเป็นจริงด้วยความสบายใจ
					ด้วยความขอบคุณ
                        </div> 
      
             
<!--  เพศ  -->
                        <div class="form-row">
                            <div class="form-group col-md-6">
                                <p>เพศ</p>
                                <div class="form-check form-check-inline">
                                    <input class="form-check-input" type="radio" name="gender" id="male" value="ชาย">
                                    <label class="form-check-label" for="male">ชาย</label>
                                </div>
                                <div class="form-check form-check-inline">
                                    <input class="form-check-input" type="radio" name="gender" id="female" value="หญิง">
                                    <label class="form-check-label" for="female">หญิง</label>
                                </div>
                                <div class="form-check form-check-inline">
                                    <input class="form-check-input" type="radio" name="gender" id="female1" value="อื่นๆ">
                                    <label class="form-check-label" for="female">อื่นๆ</label>
                                </div>
                            </div></div>
<!--  อายุ   -->

                        <div class="form-row">
                         <div class="form-group col-md-6">
                            <label for="age">อายุ</label>
                            <input type="text" class="form-control" id="age" name="age" placeholder="อายุ">
                         </div>
                                            
                        
<!--  ระดับชั้น   --> 
                            <div class="form-group col-md-6">
                            <label for="planselect">ระดับชั้น</label>
                            <select id="planselect" class="form-control" name = "plan">
                            <option selected>เลือกระดับชั้น</option>
                            <option>มัธยมศึกษาปีที่ 1</option>
                            <option>มัธยมศึกษาปีที่ 2</option>
                            <option>มัธยมศึกษาปีที่ 3</option>
                            <option>มัธยมศึกษาปีที่ 4</option>
                            <option>มัธยมศึกษาปีที่ 5</option>
                            <option>มัธยมศึกษาปีที่ 6</option>
                            </select>
                            </div> 
                            </div>  
                        
<!--ข้อ 1-->
                     <div class="alert alert-success" role="alert">
                        <h2 class="font-weight-bold">1.	โดยปกติเพื่อนใช้เครื่องมือสื่อสารชนิดใดเป็นหลัก</h2> 
                        <h6> เลือกได้มากกว่า 1 ข้อ</h6>
                        <form>
                            <Table>
                              <Tr><Td><input Type=Checkbox Name=hobby Value="Reader"> สมาร์ทโฟน</Td></Tr>
                              <Tr><Td><input Type=Checkbox Name=hobby Value="Sport"> แท็บเล็ต</Td></Tr>
                              <Tr><Td><input Type=Checkbox Name=hobby Value="Fishing"> คอมพิวเตอร์โน้ตบุ๊ค</Td></Tr>
                              <Tr><Td><input Type=Checkbox Name=hobby Value="Music"> คอมพิวเตอร์ตั้งโต๊ะ</Td></Tr>
                              <Tr><Td><input type="text" class="form-control" id="hobby" name="hobby" placeholder="อื่นๆ ได้แก่"></Td></Tr>
                            </Table>
                        </form>
                    </div> 
<!--ข้อ 2-->
                     <div class="alert alert-success" role="alert">
                        <h2 class="font-weight-bold">2.	โดยทั่วไป เพื่อนใช้เวลาในแต่ละวันกับเครื่องมือสื่อสารเฉลี่ยประมาณกี่ชั่วโมง</h2>
                        <Form>
                            <Table>
                              <TR><TD><input Type=radio Name=hobby1 Value="Reader1"> ไม่เกิน 2 ชั่วโมง/วัน</TD></TR>
                              <TR><TD><input Type=radio Name=hobby1 Value="Sport1"> 3-4 ชั่วโมง/วัน</TD></TR>
                              <TR><TD><input Type=radio Name=hobby1 Value="Fishing1"> 5-6 ชั่วโมง/วัน</TD></TR>
                              <TR><TD><input Type=radio Name=hobby1 Value="Music1"> มากกว่า 6 ชั่วโมง/วัน</TD></TR>
                            </Table>
                        </Form>
                    </div> 
<!--ข้อ 3-->
                     <div class="alert alert-success" role="alert">
                        <h2 class="font-weight-bold">3.	ช่วงโควิด19 (มีนาคม-พฤษภาคม) ที่ต้องอยู่บ้านเป็นส่วนใหญ่  เพื่อนใช้เวลาในแต่ละวันกับเครื่องมือสื่อสารเฉลี่ยประมาณกี่ชั่วโมง</h2>
                        <Form>
                            <Table>
                              <TR><TD><input Type=radio Name=hobby2 Value="Reader2"> ไม่เกิน 2 ชั่วโมง/วัน</TD></TR>
                              <TR><TD><input Type=radio Name=hobby2 Value="Sport2"> 3-4 ชั่วโมง/วัน</TD></TR>
                              <TR><TD><input Type=radio Name=hobby2 Value="Fishing2"> 5-6 ชั่วโมง/วัน</TD></TR>
                              <TR><TD><input Type=radio Name=hobby2 Value="Music2"> มากกว่า 6 ชั่วโมง/วัน</TD></TR>
                            </Table>
                        </Form>
                    </div> 
<!--ข้อ 4-->
                     <div class="alert alert-success" role="alert">
                        <h2 class="font-weight-bold">4.	ในระหว่างใช้เครื่องมือสื่อสาร เพื่อนเคยพบเห็นโฆษณาชวนให้เล่นพนันหรือเสี่ยงโชค เช่น “เล่นเกมได้เงิน” “ลงทุนง่ายได้เงินไว” หรือ “กักตัวไม่กลัวจน” หรือไม่?</h2>
                        <Form>
                            <Table>
                              <TR><TD><input Type=radio Name=hobby3 Value="Reader3"> เคย</TD></TR>
                              <TR><TD><input Type=radio Name=hobby3 Value="Sport3"> ไม่เคย</TD></TR>
                            </Table>
                        </Form>
                    </div>  

                          
<!--  ปุ่มบันทึกข้อมูล   -->      
 
                        <br>
                        <button type="submit" class="btn btn-primary btn-block">บันทึกข้อมูล</button><br>
                    </form>
                   <div class="alert alert-primary"  role="alert"><center>
                        <font size=3>จัดทำโดย</font><br>
                        <font size=3>นายอภิวัฒน์ วงศ์กัณหา ครู ชำนาญการพิเศษ</font>
                        </center></div>   
                    <div id="output"></div>
                </div>
            </div>      
        </div>
    </body>
</html>
--------------------------------------------------
  โค้ด JavaScript
--------------------------------------------------
<script>
  function preventFormSubmit() {
    var forms = document.querySelectorAll('form');
    for (var i = 0; i < forms.length; i++) {
      forms[i].addEventListener('submit', function(event) {
      event.preventDefault();
      });
    }
  }
  window.addEventListener('load', preventFormSubmit);    
      
      
  function handleFormSubmit(formObject) {
    google.script.run.processForm(formObject);
    document.getElementById("myForm").reset();
  }
</script>

