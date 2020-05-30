## Vulnerabilities in password-based login

### Brute-force attacks 
- A brute force attack is when an attacker uses a system of trial and error in an attempt to guess valid user credentials.
- Brute-forcing is not always just a case of making completely random guesses at usernames and passwords. 
- By using basic logic and publicly available knowledge, attackers can fine-tune brute force attakcs to make much more educated guesses. 
</br>

### Brute-forcing usernames 
- It is very common to see business logins in the format of `firstname.lastname@company.com`
- Even high privileged accounts are created using predictable usernames, such as `admin` or `administrator`
- Check HTTP responses to see if any email addresses are disclosed 
</br>

### Brute-forcing passwords 
- Many websites adopt some form of password policy, which forces user to create high-entropy password 
- This involves: 
..- Minimum number of characters 
..- Mixture of lower and uppercase letters 
..- At least one special character 
- Users often take a password that they can remember and try to crowbar it into fitting the password policy 
- When the policy requires users to change their passwords on a regular basis, it is also common for users to just make minor and predictable changes 
</br>

### Username enumeration  
- Typically occurs either on the login page (when you enter a valid username but an incorrect password) or on a registration for when you enter a username that is already taken.
- This reduces the time and effort required to brute-force a login because the attacker is able to quickly generate a shortlist of valid usernames 
- When brute-forcing, you should pay attention to: 
..- Status codes = if a guess returns a different status code, this is an indication that the username was correct 
..- Error messages = returned error messages can be different depending on whether both the username AND password are incorrect or just one of them is incorrect.
..- Response times = Any times that deviate suggest that something different was happening behind the scenes.

> LAB = Username enumeration via different responses
> 
> ANS = user:iloveyou 


> LAB = Username enumeration via subtly different responses
> 
> ANS = amarillo:112233

> LAB = Username enumeration via response timing 
> 
> ANS = WORK IN PROGRESS 

### Flawed brute-force protection 
- Two most common ways of preventing brute-force attacks are: 
..1 Locking the account that the remote user is trying to access if they make too many failed login attempts 
..2 Blocking the remote user's IP address if they make too many login attempts in quick succession
</br>

> LAB = Broken brute-force protection, IP block  
> 
> ANS = WORK IN PROGRESS 

### 1.Account Locking 
- One way in which websites try to prevent brute-forcing is to lock the account if certain suspicious criteria are met (amount of failed logins) 
- Account locking also fails to protect against credential stuffing attacks 
- This involves using a massive dictionary of `username:password` pairs, composed of genuine login credentials stolen in data breaches. 
- Account locking does not protect against credential stuffing because each username is only being attempted once. 
</br>

> LAB = Username enumeration via account lock 
> 
> ANS = WORK IN PROGRESS

### 2.User rate limiting 
- Making too many login requests within a short period of time causes your IP address to be blocked 
- Typically, the IP can only be unblocked in one of the following ways: 
..- Automatically after a period of time 
..- Manually by an administrator 
..- Manually by the user after successfully completing a CAPTCHA 
- As the limit is based on the rate of HTTP requests send from the user's IP address, it is possible to bypass this defense if you can work out how to guess multiple passwords with a single request
</br>

> LAB = Broken brute-force protection, multiple credentials per request 
> 
> ANS = WORK IN PROGRESS

### HTTP basic authentication
- The client recieves an authentication token from the server, made up from concatenating the username and password and encoded in base64 
- This token is stored and managed by the browser and add an `Authorisation` header of every subsequent request
- The syntax is as follows: `Authorization: Basic base64(username:password)
- User credentials are prone to being captured in a man-in-the-middle attack 
- It is vulnerable to session-related exploits as it offers no protection on its own  


