# SpringSecurityUsingCustomLogin
Enabling spring security using custom login page.

Spring-security provides a default built-in login page, which has two text boxes to enter the Username and Password, and a Submit button to submit the credentials for validation. You don't have to design a login form for your application. As soon as the user opens the application url on his browser, spring-security checks if the user has not log in, then it redirects the user to the default login form provided by spring-security.

If you want to use a custom login page for your application, then you can configure spring-security to use your custom login page instead. You can use the <security:form-login> tag to define your custom login form page within the <security:http> … </security:http> tag. Below is the configuration example.

         <security:form-login login-page="/login"
                             default-target-url="/userpage"
                             login-processing-url="/j_spring_security_check"
                             authentication-failure-url="/accessdenied"
                             username-parameter="username"
                             password-parameter="password"
                />

        <!-- Logout -->
        <security:logout logout-success-url="/logout" />


login-page: Custom login page url path.
default-target-url : url where the user should navigate after successful login.
authentication-failure-url: url where the user should navigate after a login failure.
username-parameter and password-parameter : username-parameter and password-parameter - These two are optional. By default spring-security accepts the parameter names “j_username” and “j_password” as username and password in the login form. If you want to given any other name to the username and password input fields in the login form, then you can specify the custom parameter names in these two attributes in <security:form-login ...> tag.

In “logout-success-url” you can specify the page url path which should execute when user uses spring-security logout process.

# Build 
mvn clean install

