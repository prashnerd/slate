---
title: Gametize API 

language_tabs: # must be one of https://git.io/vQNgJ
  - java
  - python
  - javascript
  - shell

toc_footers:
  - <a href='#authentication'>Where can I get my API key?</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - changelog
  - authentication
  - challenges
  - users
  - claims
  - games
  - bundles
  - notifications
  - items
  - teams
  - login
  - register
  - actions
  - errors

search: true
---
  
# Introduction

> Gametize API Documentation

```java
                                                                              
      ######    #####    ### ###   #######  ########  #  #######  #######     
     #      #  #     #  #   #   #  #           #      #       #   #           
     #         #     #  #   #   #  #           #      #      #    #           
     #         #######  #   #   #  ######      #      #     #     ######      
     #    ###  #     #  #   #   #  #           #      #    #      #           
     #      #  #     #  #   #   #  #           #      #   #       #           
      ######   #     #  #   #   #  #######     #      #  #######  #######     
                                                                              
                                                                              
                 ###########################################                  
               ###############################################                
              #################################################               
              #################################################               
              #################################################               
              #################################################               
              ###                                           ###               
              ##                                             ##               
              ##        #####                  #####         ##               
              ##       #     #                #     #        ##               
              ##                                             ##               
              ##                  #      #                   ##               
              ##                   ######                    ##               
              ###                                           ######            
               ###################################################            
                  ###############################################             
                 ###########################################                  
               #########################################                      
             ######  ###################################                      
            ######   ###################################                      
            #####    ###################################                      
                     ###################################                      
                     ###################################                      
                     ###################################                      
                     ###################################                      
                     #######                     #######                      
                      ####                         ####                       
                                                                              
```

```python
                                                                              
      ######    #####    ### ###   #######  ########  #  #######  #######     
     #      #  #     #  #   #   #  #           #      #       #   #           
     #         #     #  #   #   #  #           #      #      #    #           
     #         #######  #   #   #  ######      #      #     #     ######      
     #    ###  #     #  #   #   #  #           #      #    #      #           
     #      #  #     #  #   #   #  #           #      #   #       #           
      ######   #     #  #   #   #  #######     #      #  #######  #######     
                                                                              
                                                                              
                 ###########################################                  
               ###############################################                
              #################################################               
              #################################################               
              #################################################               
              #################################################               
              ###                                           ###               
              ##                                             ##               
              ##        #####                  #####         ##               
              ##       #     #                #     #        ##               
              ##                                             ##               
              ##                  #      #                   ##               
              ##                   ######                    ##               
              ###                                           ######            
               ###################################################            
                  ###############################################             
                 ###########################################                  
               #########################################                      
             ######  ###################################                      
            ######   ###################################                      
            #####    ###################################                      
                     ###################################                      
                     ###################################                      
                     ###################################                      
                     ###################################                      
                     #######                     #######                      
                      ####                         ####                       
                                                                              
```

```javascript
                                                                              
      ######    #####    ### ###   #######  ########  #  #######  #######     
     #      #  #     #  #   #   #  #           #      #       #   #           
     #         #     #  #   #   #  #           #      #      #    #           
     #         #######  #   #   #  ######      #      #     #     ######      
     #    ###  #     #  #   #   #  #           #      #    #      #           
     #      #  #     #  #   #   #  #           #      #   #       #           
      ######   #     #  #   #   #  #######     #      #  #######  #######     
                                                                              
                                                                              
                 ###########################################                  
               ###############################################                
              #################################################               
              #################################################               
              #################################################               
              #################################################               
              ###                                           ###               
              ##                                             ##               
              ##        #####                  #####         ##               
              ##       #     #                #     #        ##               
              ##                                             ##               
              ##                  #      #                   ##               
              ##                   ######                    ##               
              ###                                           ######            
               ###################################################            
                  ###############################################             
                 ###########################################                  
               #########################################                      
             ######  ###################################                      
            ######   ###################################                      
            #####    ###################################                      
                     ###################################                      
                     ###################################                      
                     ###################################                      
                     ###################################                      
                     #######                     #######                      
                      ####                         ####                       
                                                                              
```

```shell
                                                                              
      ######    #####    ### ###   #######  ########  #  #######  #######     
     #      #  #     #  #   #   #  #           #      #       #   #           
     #         #     #  #   #   #  #           #      #      #    #           
     #         #######  #   #   #  ######      #      #     #     ######      
     #    ###  #     #  #   #   #  #           #      #    #      #           
     #      #  #     #  #   #   #  #           #      #   #       #           
      ######   #     #  #   #   #  #######     #      #  #######  #######     
                                                                              
                                                                              
                 ###########################################                  
               ###############################################                
              #################################################               
              #################################################               
              #################################################               
              #################################################               
              ###                                           ###               
              ##                                             ##               
              ##        #####                  #####         ##               
              ##       #     #                #     #        ##               
              ##                                             ##               
              ##                  #      #                   ##               
              ##                   ######                    ##               
              ###                                           ######            
               ###################################################            
                  ###############################################             
                 ###########################################                  
               #########################################                      
             ######  ###################################                      
            ######   ###################################                      
            #####    ###################################                      
                     ###################################                      
                     ###################################                      
                     ###################################                      
                     ###################################                      
                     #######                     #######                      
                      ####                         ####                       
                                                                              
```

<aside class="warning">
Gametize's current API specification is <strong>only open to paid plans</strong>, and the instructions below are only applicable to those users. Don't worry though: the platform will soon be open to all!
</aside>

**Introduction to Gametize API** Here are some fluffy words for introducing the Gametize API and explaining how it should be used. This section has been deliberately made longer so that we can see how it looks like when there's more text.

And hey, here's another paragraph to *really* fill this bit out. LALALALA APIs ARE AWSOME WOOOOOOOOO. Do you like my ninja on the right? It did *not* take me all night, I swear! 

I think that should do it for placeholder text... Enjoy the rest of the documentation!

<s>To fill space</s> To help you understand this document better, here are some examples of the types of "*alerts*" you can expect to see. 

<aside class="notice">These <em>calming, unbotrusive cyan alerts</em> provide notices or information about the content preceding them. For example, these notices may be used to remind you of certain actions you may need to perform to get a particular API call to work.</aside>
<aside class="warning">These <strong>scary red alerts</strong> warn you about certain conditions that need to be fulfilled for the API to work, or they may warn you about certain things you should take care of. For example, these warnings may warn you about some special requirements for an API call.</aside>
<aside class="success">These <em>helpful, green alerts</em> serve to reinforce best practices when making your appliation. For example, these reinforcement notices may be used to tell you when and how to make certain API calls or when to use that particular API call.</aside>
<aside class="dev">These <em>puzzling, obscure, yellow alerts</em> are development notes, put in place by the incrediby nerdy developer(s) for their own internal reference. If you see these alerts in a particular section, you may assume that it is currently under development or may be revised soon for you to get the best performance out of our Gametize API!</aside>
<aside class="quote">These <em>whimsical, pink, specially-formatted alerts</em> are quotes taken from someone or somewhere to give better context to the the content. For example, these quotes may highlight what other API providers have to say on specific issues or may simply be taken from anyone who has made a relevant comment.</aside>

Now that we're done getting to know each other better, let's get to know the **Gametize API** better!

# Terminology

>This section on the right will display sample code for you to refer to when making your API calls. Switch between the different languages in the tabs located at the top! Note that some parameters and JSON fields may be obfuscated with asterisks (\*) or some placeholder text, but the structure of the returns are preserved as much as possible. Please note that the number of asterisks does not indicate the character count/length of the value.

To aid in platform administration, Gametize has **redefined terms** found in the Admin Dashboard to showcase a more logical correlation between entities. However, **the terms are left unchanged in the API**, as it might be disruptive to live applications. Please take note of the following:

Name in API | Name in Admin Dashboard
:---:|:---:
Bundle | Project
Game | Topic
Challenge | Challenge (unchanged)

<aside class="dev">Update all the warnings for <code>session_key</code> to reflect the new "Authorization-Bearer" schema. EDIT: should be done already, but check to make sure.</aside>
