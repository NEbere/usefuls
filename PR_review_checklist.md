Things to check in Ruby code review:
- Code readability check https://github.com/rubocop-hq/ruby-style-guide also https://github.com/rubocop-hq/rails-style-guide
- Check if conventions in code base is followed
- Check that the right types are used: array, object, enums etc
- if new packages are used, check that they saved in gem file with latest versions 
- Check if the changes made are done in the right file/folder/component/class
- Check for code duplicates for newly defined logic/methods/classes and see if anything can be reused that already exist or if it could be made a re-usable utility function
- Should the implemented changes be monitored via a logging system or alert set (like cloud watch or other logging/alerting platforms)
- Are there any changes that need configuration details? Like database, ports, are these configurations provided, and added to the necessary containerisation tool used (docker)
- Will the test pass for Travis build? Any missing config needed in Travis file?
- Are the version changes updated in config files? Eg: rails version

Guides:
https://thoughtbot.com/blog/code-review-ruby-and-rails-idioms

TODO
- Make personal code review checklist and ensure to remember it. Let it be generic and also specific as possible. Have sections for frameworks/languages If needed
- Look at:
https://blog.codinghorror.com/code-smells/
https://github.com/mestachs/experiment/blob/master/codereview/checklist.md
https://matthewpaulmoore.com/post/5190436725/ruby-on-rails-code-quality-checklist
https://www.codementor.io/blog/code-review-checklist-76q7ovkaqj
https://www.bignerdranch.com/blog/the-4-things-we-look-for-in-a-code-review/
https://www.google.com/search?q=ruby+code+review+checklist&sa=X&ved=2ahUKEwiLh4WK7afkAhUTTsAKHYBHA4EQ1QIoAHoECAoQAQ
https://www.google.com/search?q=code+review+best+practices&sa=X&ved=2ahUKEwiLh4WK7afkAhUTTsAKHYBHA4EQ1QIoBHoECAoQBQ
https://www.google.com/search?q=code+review+principles&sa=X&ved=2ahUKEwiLh4WK7afkAhUTTsAKHYBHA4EQ1QIoBXoECAoQBg
https://www.google.com/search?q=how+to+get+better+at+code+reviews&sa=X&ved=2ahUKEwiLh4WK7afkAhUTTsAKHYBHA4EQ1QIoAnoECAoQAw
https://www.google.com/search?q=code+review+approaches&sa=X&ved=2ahUKEwiLh4WK7afkAhUTTsAKHYBHA4EQ1QIoB3oECAoQCA
https://reinteractive.com/posts/126-checklist-for-a-rails-application-code-audit
https://softwareengineering.stackexchange.com/questions/54814/how-to-evaluate-the-quality-of-rails-code
https://www.google.com/search?q=reviewing+ruby+code&ei=TKZnXYuxEJOcgQaAj42ICA&start=10&sa=N&ved=0ahUKEwiLh4WK7afkAhUTTsAKHYBHA4EQ8NMDCKoB&biw=1440&bih=821&dpr=2
https://www.airpair.com/ruby-on-rails/rails-code-review


How to setup automatic deployment with GitHub and travis and aws
Blog post and video



What to do in case of an error:
- locate where that rollbar is been called in code
- add more details to the rollbar or remove it to get all the error details by default



Model/Payload/Request body
- when models are created and tested, check if some  fields are required and if they are tested according
- check if fields have default values where needed and that this is tested in specs



Error handling:
- check that error is handled properley, especially with external dependencies.
eg: call to external API, system or third party. handle such carefully
and check that error does not fail the whole system.

- If new error is thrown, ensure it uses the right type and has the right error message
throwing Error with strings is not maintainable, not a good practice and difficult to test.

- In async/await in JS, ensure error is caught/handled. either catch on the await or use a try and catch so
an error doesnt break the code because it is "unhandled" 



Logging:
- check what is logged, is it important, is it too much, is it just enough?
bearing in mind that excessive logging can affect application performance
as it is also a request or code to be run


Testing
- if test setup is too much effort then maybe investigate the process
- check that new changes didnt affect or change existing test or business logic
- if a function or method is async, its stub should be async as well and vice versa
- randomize test and check that there no dependencise between specs and no context leaks
- if a value is tested, test the inverse of it to see that it is working as expected

Business:
- check that the changes work well with the defined ticket
- check that the change works as expected with the entire flow
- 



Architecture:
- does this change need to be documented in overall system architetcure document, wiki, README?
