function validate()
{
   var uname = student.uname.value;
   var pass = student.pass.value;
   var fname = student.fname.value;
   var lname = student.lname.value;
   var email = student.email.value;
   var course = student.course.selectedIndex;
   var pnumber = student.pnumber.value;
   var dept = student.dept.selectedIndex;
   var message ="";
   var flag = false;
   var efilter = /^([a-zA-Z0-9\_\.\-])+\@(([a-zA-Z0-9\-])+\.)+([a-zA-Z0-9]{2,4})+$/;
   var lchar = /^([a-zA-Z])$/;

   if(uname.trim()=="")
   {
      flag=true;
      message += " Username should not be blank!\n";
   }

   if(pass.trim()=="")
   {
      flag=true;
      message += " password is required!\n";
   }

   if(!lchar.test(fname))
   {
      flag=true;
      message += " Firstname should contain only letters!\n";
   }

   if(lname.trim()=="")
   {
      flag=true;
      message += " Lastname should not be blank!\n";
   }

   if(student.gender[0].checked==false && student.gender[1].checked==false)
   { 
      flag=true;
      message +=" Gender is not Selected!\n";
   }
    
   if(!efilter.test(email))
   {
      flag=true;
      message += " Email is not valid!\n";
   }
  
   if(course==0)
   {
      flag=true;
      message += " Course is not selected!\n";
   }

   if(dept==0)
   {
      flag=true;
      message += " Department is not selected!\n";
   }
	
   if(isNaN(pnumber) || pnumber.length!=12)
   {
      flag=true;
      message += " Mobile number is not valid!\n";
   }

   if(flag)
   {
      alert("Warning!!!\n"+ message);
      return false;
   }
   return true;
}
     


   