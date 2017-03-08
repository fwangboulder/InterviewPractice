# InterviewPractice
##Answer the interview questions as if answering them in an interview for a specific job.(6 total)


###1. What is the most influential book or blog post you’ve read regarding web development?
I have been reading the full stack python by Matthew Makai, a Developer Evangelist. This is mainly my guidance book because it gives short description about all concepts in web development and provides rich resources links for me to follow. I have to say this is the book opening the door of web development for me.  Together with this full stack web developer program, I have been addicted to build awesome web apps. I will keep using this book as a tool to learn more about emerging web technologies and improve my skills of web development in future.   

###2. Tell me about a web application you have built. Why did you choose to build it? What did you learn? What challenges did you face and how did you overcome them?
I built a web application featuring a map of my neighborhood trails. Users can search all included landmarks and when selected, additional information about this landmark is presented
from the FourSquare and Wikipedia APIs. I learned how design patterns assist in developing
a manageable codebase and how frameworks can decrease the time required developing an application and provide a number of utilities for me to use. I also learned to implement third-party APIs that provide valuable data sets that can improve the quality of my application. I used knockout framework, which is new to me. I had to hard time to apply it
and make all data incorporated correctly for display. I read carefully about the help documentation of knockout about data-bind and also get help from experienced people.

###3. Write a function in Python that takes a list of strings and returns a single string that is an HTML unordered list of those strings. You should include a brief explanation of your code. Then, what would you have to consider if the original list was provided by user input?
```Python
def unordered_list(strings):
    """
    :type strings: List[str]
    :rtype: str
    #This function returns an html unordered list.
    """
    # creating the left side of unordered list tag

    lst = '<ul>'

    # for loop : iterate over strings
    for s in strings:

        # append list item tag with contents of one element in strings
        lst += '<li>%s</li>' % s

    # append right side of unordered list tag
    lst += '</ul>'
    return lst

```

If the original list was provided by user input, I need to check if the input is efficient first. The function should be able to check whether the input is a list,and whether the list contains strings.

###4. List 2-3 attacks that web applications are vulnerable to. How do these attacks work? How can we prevent those attacks?
* Injections let attackers modify a back-end statement of command through unsanitized
user input.All injections attacks involve allowing untrusted or manipulated requests,
commands or queries to be executed by a web application.
To prevent the weakness, you can use a vetted Library or framework, use an API which avoids
the use of an interpreter, run the application with minimum privileges, escape all special characters used by an interpreter, and set the input validation/sanitization, white list only allowed characters.
* Broken Authentication and Session Management allows the capture or bypass of authentication methods used to protect against unauthorized access. The most commonly used authentication scheme is the use of a Username and Password that generates a Session ID.The web application should protect these values and not allow attackers to steal them to impersonate users.To prevent this attack, stored Username and Password information should be encrypted, along with salting and hashing the values to make it more difficult to extract if the values fall into the wrong hand.
* Cross_Site Scripting lets attackers insert Javascript in the pages of a trusted site. By doing so, they can completely alter the content of the site to do their bidding. To prevent this, you can use a vetted Library or framework. Also, in any situation where data will be output to a page, especially data that was received from external inputs, use encoding for non-alphanumberic characters. You also can set all cookies with the HTTP only attribute, and this will make the cookies be protected from being accessible to malicious client side scripts that sue document.cookies. Input validation will always help with this.  

###5. Here is some starter code for a Flask Web Application. Expand on that and include a route that simulates rolling two dice and returns the result in JSON. You should include a brief explanation of your code.
  ```
from flask import Flask
app = Flask(__name__)

import json
import random

@app.route('/')
def hello_world():
return 'Hello World!'

if __name__ == '__main__':
app.debug = True
app.run()

  ```
First I need to do is to add a new route @app.route('/roll_dices/json')  
Then I need to create a function which can roll two dices, return the result as a json
format. I need to import two modules: json and random.



I've added the functionality to roll two dice and return the result as a json string.
  I've included the ability to pass the number of sides the dice have to the function since it wasn't specified and expands the functionality.
  The result of each die roll is assigned to a variable. The function returns the results of json.dumps(), sorted by key.
  ```python

  from flask import Flask
  app = Flask(__name__)

  import json
  import random

  @app.route('/')
  def hello_world():
      return 'Hello World!'

  # Create the route
  @app.route('/roll_dices/json')
  def roll_dices():
      """
      :rtype: str
      #This function rolls two dices and returns the result in json format
      """

      # Assign the result of the dice roll, assuming the dice has six sides.
      # dice 1
      dice1 = random.randint(1, 6)
      # dice 2
      dice2 = random.randint(1, 6)

      # Return the results of the dice rolled as json string, sorted by key
      return json.dumps({'dice1': dice1, 'dice2': dice2}, sort_keys=True)

  if __name__ == '__main__':
      app.debug = True
      app.run()

  ```


###6. If you were to start your full-stack developer position today, what would be your goals a year from now?

I will never stop to improve and update my skills. One year from now, I believe I will have made the best practices of what I have known in your company. I am so excited that I will have the opportunity to join an ambitious and inclusive workplace. I will probably have learned a lot from company colleagues and I am always ready to help other people to learn and grow too. In addition to the job, I will finish most courses required by the online Master of Science in Computer Science of Georgia Tech University in my spare time. I want to learn more and dive deeper. With all the skills I have, I want to build my personal website which displays all my achievements and study progress to public. I always want to show my new skills and use it.  
