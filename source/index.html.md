---
title: Gametize API 

language_tabs: # must be one of https://git.io/vQNgJ
  - java
  - python
  - javascript
  - shell

toc_footers:
  - <a href='#'>Where can I get my API key?</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
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

And hey, here's another paragraph to *really* fill this bit out. LALALALA APIs ARE AWSOME WOOOOOOOOO. Do you like my ninja on the right? It did *not* take me all night, I swear! This introduction though. Really feels like the ramblimgs of a madman doesn't it? ***Or*** maybe that's what I *want* you to think! Isn't that *spooooooooky*? Have I written enough yet? Hmm, doesn't quite look like it is... Tell you what: I won't tell if *you* don't!

<s>To fill space</s> To help you understand this document better, here are some examples of the types of "*alerts*" you can expect to see. 

<aside class="notice">NOTICE <em>NOTICE</em> <strong>NOTICE</strong> <strong><em>NOTICE</em></strong> </aside>
<aside class="warning">WARNING <em>WARNING</em> <strong>WARNING</strong> <strong><em>WARNING</em></strong> </aside>
<aside class="success">SUCCESS <em>SUCCESS</em> <strong>SUCCESS</strong> <strong><em>SUCCESS</em></strong> </aside>

I MADE THE FOLLOWING TWO MYSELF.

<aside class="dev">DEVELOPMENT NOTES <em>DEVELOPMENT NOTES</em> <strong>DEVELOPMENT NOTES</strong> <strong><em>DEVELOPMENT NOTES</em></strong> </aside>
<aside class="quote">QUOTE <em>QUOTE</em> <strong>QUOTE</strong> <strong><em>QUOTE</em></strong> </aside>

***PATS SELF ON BACK***

Okay, fine, I *may* have referred to the previous ones ***but still!*** 

> AM I A FRONTEND DEV NOW AAAAAAAAAAHHHHHHHH I FEEL A COMPULSIVE NEED TO FORMAT THINGS!!!


# Terminology

To aid in platform administration experience, Gametize has **redefined terms** found in the Admin Dashboard to showcase a more logical correlation between entities. However, **the terms are left unchanged in the API**, as it might be disruptive to live applications. Please take note of the following:

Name in API | Name in Admin Dashboard
:---:|:---:
Bundle | Project
Game | Topic
Challenge | Challenge (unchanged)

<aside class="dev">Update all the warnings for <code>session_key</code> to reflect the new "Authorization-Bearer" schema.</aside>
