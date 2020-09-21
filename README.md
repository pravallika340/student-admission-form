# student-admission-form
student admission form
<!DOCTYPE html>
<html lang="en">
<head>
  <title>jquery Validation Example</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/css/bootstrap.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/js/bootstrap.min.js"></script>
 
</head>

       
<body>
    <div class="container">
            <h2>Student Admission form</h2>
            <form >
                <div class="form-group">
                <label for="user">First Name</label>
                <input type="user" tabindex="1" class="form-control" id="user" placeholder="Enter First Name" name="user" autocomplete="off">
                <span id="user_error"></span>
                </div>
                <div class="form-group">
                    <label for="user1">Last Name</label>
                    <input type="user" tabindex="2" class="form-control" id="last" placeholder="Enter Last Name" name="user" autocomplete="off">
                    <span id="user1_error"></span>
                    </div>
                <div class="form-group">
                <label for="pass">class</label>
                <input type="class" tabindex="3" class="form-control" id="pass" placeholder="Enter class" name="pass" autocomplete="off">
                <span id="pass_error"></span>
                </div>

                <div class="form-group">
                    <label for="year" tabindex="4">Passing Year</label>
                    <select class="form-control" id="year">
                        <option>select</option>
                        <option>2017</option>
                        <option>2018</option>
                        <option>2019</option>
                        <option>2020</option>
                      </select>
                    <span id="year_error"></span>
                    </div>

                <div class="form-group">
                <label for="percentage">Percentage</label>
                <input type="number" tabindex="3" class ="form-control" id="percentage" placeholder="enter your percentage" name="percentage" autocomplete="off">
                <span id="percentage_error"></span>
                </div>
                 <button type="button" onclick="submitform()" tabindex="6 " id="submit" class="btn btn-primary" >Submit</button>
            </form>
       
            
        </div>

          </div>
        <script>
        $(document).ready(function(){
            $('#user_error').hide();
            $('#user1_error').hide();
            $('#pass_error').hide();
            $('#year_error').hide(); 
            $('#percentage_error').hide();
        });
        var user_status = true;
        var user1_status = true;
        var pwd_status = true;
        var year_status = true;
        var percentage_status = true;
        $('#user').keyup(function(){
            userCheck();
        });
        $('#last').keyup(function(){
            user1Check();
        });
        $('#pass').keyup(function(){
            pwdCheck();
        });
        $('#year').keyup(function(){
            yearCheck();
        });
        $('#percentage').keyup(function(){
            percentageCheck();
        });
        
        // username

        function userCheck(){
            var userval = $('#user').val();
            var u=/^[A-Za-z0-9@#$%^&*!]{4,20}$/;
            if(!userval.match(u)){
                $('#user_error').show();
                $('#user_error').html("User name must be between 4 and 20 characters");
                $('#user_error').css("color","brown");

                user_status=false;
            }

            else{
                $("#user_error").hide();
            }
        }
        // last name

        function user1Check(){
            var userval = $('#last').val();
            var u=/^[A-Za-z0-9@#$%^&*!]{4,20}$/;
            if(!userval.match(u)){
                $('#user1_error').show();
                $('#user1_error').html("User name must be between 4 and 20 characters");
                $('#user1_error').css("color","brown");

                user1_status=false;
            }

            else{
                $("#user1_error").hide();
            }
        }

        // Password

        function pwdCheck(){
            var pwdval = $('#pass').val();
            var h=/^(?=.*[0-9])(?=.*[a-zA-Z])([a-zA-Z0-9]+)$/
            // var h=/^(?=.*?[A-Z])(?=.*[a-z])(?=.*?[0-9])(?=.*?[!@#$%^&*_-]).{8,14}$/;
            if(!pwdval.match(h)){
                $('#pass_error').show();
                $('#pass_error').html("Your Class must be atleast one number and one alphabate Eg:5A ");
                $('#pass_error').css("color","brown"); 

                pwd_status = false;
            }
            else{
                $("#pass_error").hide();
            }
        }

        //percentage

        function percrntageCheck(){
            var perval=$('#percentage').val();
            var e=/^[0-9]+$/;
            // var e=/^\w+@[a-zA-Z]+?\.[a-zA-Z]{2,3}$/;
            if(!perval.match(e)){
                $('#percentage_error').show();
                $('#percentage').html("enter your year must be numbers ");
                $('#percentage_error').css("color","brown"); 

                percentage_status = false;
            }
            else{
                $("#percentage_error").hide();
            }
        }
       
        //submit

        $('#submit').click(function(){

        user_status = true;
        pwd_status = true;
        year_status = true;
        user1_status=true;
        percentage_status=true;

        userCheck();
        user1Check();
        pwdCheck();
        yearCheck();
       percentageCheck();
       
        if( user_status == true && user1_status == true && pwd_status == true && year_status == true && percentage_status == true)
            {
                return true;

            }else{
                return false;
            }
        });

        </script>

    
</body>
</html>
