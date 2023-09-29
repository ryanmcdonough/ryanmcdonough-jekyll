
Legal tech products are drawing substantial investment. Yet, the endeavor to replicate such tech in-house poses a challenge. Not every firm boasts the capability to develop a state-of-the-art legal language model or grasp the intricacies of AI-supported automated document review. 

**However**, there are other high-impact improvements attainable if we initially concentrate on mechanising merely the mundane tasks – the sort that budding lawyers didn't dream about, the ones not shown in Suits.

Imagine securing a large re-organisation project with about 400 entities, each requiring verification of on-file details accuracy. And what if the onus to draft a diligence questionnaire for this behemoth task falls on you? You understand what questions need answering to achieve this however crafting questions that are comprehensive, yet easily decipherable for the respondents is no easy feat - **it’s not necessarily what you signed up for**. Oh and of course it needs doing as soon as possible because there’s a lot of work that needs doing once the questionnaire is ready.

Now, between you and me **do you know your firm's stance on contractions and times** when drafting? Of course you do, you know all of the 40 sections from the style guide and how they apply when drafting a contract vs writing a question for a form.

Okay, so we have our problem we need to write succinct questions for a due diligence questionnaire that is easily readable by the respondent but is also consistent with our style book and most importantly that style is consistent across the 15 or so questions we draft.

**So how can we help in the tools we build?**

So we have a basic form builder here, where users can add a question - let's add that inital question I've drafted to find out about employee overtime.

  
  ![Image of a basic single input form builder](https://ryanmcdonough.co.uk/assets/img/uploads/form-1.png)
  

Let's start with the form building aspect, we can incorporate code that briefs our generative AI system on the specific stylebook - as well as the overall aims. We can start to craft a prompt like this:

    Rephrase the given question: ${question} for a Due Diligence Questionnaire to make it concise and easy to understand.
    
    Note: Avoid contractions, use the 12-hour clock for time, and specify "noon" or "midnight" instead of "12 a.m." or "12 p.m.".
      
    Provide your response in the JSON format below:
    
    { "question": string }


Great - let’s add that into our form builder code base so when the user has finished writing their question, voila - a recommendation appears to the side which they can choose to accept or not. We're not automating people's roles , we're just trying to help people get their job done quicker.

  ![Form builder showing a Gen AI suggestion of question improvement](https://ryanmcdonough.co.uk/assets/img/uploads/form-2.png)
  

**But Ryan, I hear you say: “They don’t know why it’s changed” - very good point.**

Let’s update the prompt:

    Provide your response in the JSON format below, explaining the modifications made:
    
    { "question": string, "explanation" : string }

  
![Form builder showing a Gen AI suggestion of question improvement as well as reasoning](https://ryanmcdonough.co.uk/assets/img/uploads/form-3.png)

And there we have it a simple addition to a system that will allow for anyone to start drafting the questions knowing that they’ll be improved to be more succinct as well updated to follow the style book of their firm.
