# view system 

from django . shortcuts import render
from django .contrib.auth.models import user,auth

def login(request)
    if request.method=='POST';
    username = request.POST['username']
    password = request.POST['password']
    
    user = auth.authenticate(username=username,password=password)
    
    if user is not none:
        auth.login(request,user)
        return redirect("/")
    
    else:
        messages.info(request,'invalid credentials')
        return redirect ('login')
    
    else:
        return render(request, 'register.html')

def register ( request )

if request.method == 'POST':
    first name = request.POST['First_Name']
    last name = request.POST['Last_Name']
     username= request.POST['username']
    email = request.POST['email']
    password1 = request.POST['password1']
password2 = request.POST['password2']

user.object.create_user(username=username, password=password1, email=email, first_name=first_name, last_name=last_name)
user.save();
print('user created')
return redirect('/')

else:

    return render(request,'register.html')
    
    
    
    #Registration system : 
    <!DOCTYPE html>
<html>
<head>
      <title>Registration</title>
</head>
<body>
      <form action = "register" method ="post">
{% csrf_token %}

<input type ="text" name ="First_Name" placeholder="First Name"><br>
<input type ="text" name ="Last_Name" placeholder="Last Name"><br>
<input type ="text" name ="username" placeholder="username"><br>
<input type ="email" name ="email" placeholder="email"><br>
<input type ="password" name ="password1" placeholder="password"><br>
<input type ="password" name ="password2" placeholder="confirm password"><br>
<input type = "submit>"
</html>
</body>



##Log in System##
<!DOCTYPE html>
<html>
<head>
      <title>Registration</title>
</head>
<body>
      <form action = "login" method ="post">
{% csrf_token %}
<input type = "text" name = "username" placeholder="username"><br>
<input type = "password" name = "password" placeholder="password"><br>
<input type ="submit">
</form>




<div

{% for message in messages %}
    <h3> {{message}} </h3>
{% endfor %}

</div>
</html>
</body>
