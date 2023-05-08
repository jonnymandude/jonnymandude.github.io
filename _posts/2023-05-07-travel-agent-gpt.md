---
layout: post
title: Flask Material Kit + OpenAI API = Travel Agent?
subtitle: Combining ChatGPT and Flask Material Kit to create some fun trip itineraries
cover-img: /assets/img/travel_time.jpeg
thumbnail-img: /assets/img/openai.png
gh-repo: jonnymandude/openai-travel-recommender
gh-badge: [star, follow]
tags: [openai, flask, material_kit, gpt]
---

If you've visited San Francisco or any online forum within the last few weeks, you've been surely inundanted with stories about the AI revolution. These conversations start and end with Sam Altman's dreamchild: ChatGPT. Ever since ChatGPT began to break headlines, everyone wanted to see how they could wrangle this new tool to do their menial tasks. High schoolers started writing essays, subpar boyfriends started writing apology letters to their significant others and VCs now fired their tweet ghost writers and turned to this automated tool of the future. Not dystopian at all.

Seeing this, I wanted to get a little automation in my own life. One of the things I'm worst at is making plans when travelling. Thankfully, I usually travel with friends who are excellent planners, so this isn't an issue. However, my ego could always use a nice dopamine hit, so I figured I'll impress my pals with some travel plans, courtesy of OpenAI. 


## Flask Material Kit

<a href="https://github.com/app-generator/flask-material-kit">Flask Material Kit</a> is a batteries included full-stack boiler plate for Flask. It'll help you get up and running with preconfigured auth, page templates and more. Such as the case with most tools, it's got a freemium model, allowing developers to test the waters before the bring out the Brex. 

![Example Layouts](https://user-images.githubusercontent.com/51070104/167396765-c88b7a95-155f-4236-8691-7b80fa2d9cd9.png){: .mx-auto.d-block :}

We'll make some small tweaks to integrate with a basic ChatGPT Client

## Lets Get Started

Now, we'll start with some very basic templates and create a basic travel form that asks information about one's trip. Let's try it out with some Chicago recommendations

![Chicago Recommendation](/assets/img/Chicago_request.png){: .mx-auto.d-block :}

By simply taking this input and putting into a templated API request, we can return some useful information to the user. Here's our first result. 

```
There are a lot of great things to do in Chicago! Here are some recommendations based on your interests: 

Baseball: - If you're a fan, you should definitely try to catch a game at Wrigley Field, home of the Chicago Cubs. The Cubs are playing the Arizona Diamondbacks at home on July 14 and 15. Even if you're not a big baseball fan, the historic stadium and atmosphere are worth experiencing. 

Beer: - Take a brewery tour! There are several great local breweries in Chicago, including Revolution Brewing, Half Acre Beer Company, and Goose Island Brewery. Many of them offer tours of their facilities and tastings of their brews. - Check out one of the many beer festivals happening in Chicago during the summer, such as the Windy City Smokeout (July 16-18) or the Chicago Craft Beer Festival (July 17-18). 

Local food: - Chicago is known for its deep-dish pizza, so you definitely need to try that while you're here. Some popular places to get it include Lou Malnati's, Giordano's, and Pequod's Pizza. - Another local specialty is Chicago-style hot dogs, which are served with mustard, relish, onions, pickles, tomatoes, and celery salt (but no ketchup!). You can find these at many hot dog stands around the city, but some popular spots include Portillo's and Superdawg. - If you're looking for something a little more high-end, try a steakhouse like Gibson's or Chicago Cut Steakhouse. 

Architecture: - Chicago is known for its architecture, so you might want to take an architecture boat tour on the Chicago River. These tours will take you past some of the city's most famous buildings and offer insights into their history and design. - Another option is to take a walking tour of a specific neighborhood, such as the Loop or the Magnificent Mile, and learn about the different styles of architecture represented there. - If you're interested in skyscrapers specifically, you could visit the Willis Tower (formerly the Sears Tower) or the John Hancock Center, both of which have observation decks with great views of the city. Hope this helps, and have a great trip to Chicago!

```

### The Good
ChatGPT really knows a lot. It has a terrific grasp of general knowledge about people places and things. Some of the Chicago specific knowlege of restaurants and architecture is absolutely astounding. In addition, some of the schedule specific information about the City Smokeout and Beer Festival is incredibly impressive. 

Furthermore, the ability to take in unstructured text input makes it incredibly useful for building. Limited cleaning and grooming needs to take place before we send a message over to GPT. 

### The Bad / The Ugly
Hallucinations. The Cubs have a series with Red Sox that week. They're referencing last years schedule. Not a problem, but really not something that we would want to trust. As a result, it may be wise to ask for general suggestions from a tool like this.

Let's give it another chance with a different trip

![Rome Recommendation](/assets/img/Rome_recc.png){: .mx-auto.d-block :}

```
1. Visit the Colosseum: As a fan of ancient history, the Colosseum is a must-see. You can take a guided tour or explore on your own and learn about the history of the famous amphitheater.

2. Tour the Vatican Museums: As the headquarters of the Catholic Church, Rome is full of important Catholic landmarks. The Vatican Museums include the Sistine Chapel, St. Peter's Basilica and a large collection of art and artifacts. 

3. Take a cooking class: Since you are interested in pasta, why not learn how to make it yourself? There are several cooking classes in Rome that cater to tourists. 

4. Visit the Pantheon: One of the best-preserved ancient buildings in Rome, the Pantheon is a must-visit for anyone interested in ancient architecture. 

5. Go on a wine tasting tour: Italy is famous for its wines, so why not take a wine tasting tour? You can explore the vineyards of nearby regions like Tuscany or take a tour of Rome's wine bars. 

6. Visit the Trevi Fountain: One of the most famous fountains in the world, the Trevi Fountain is a popular tourist attraction. You can throw a coin in the fountain and make a wish. 

7. Take a walk through Trastevere: This bohemian neighborhood is full of restaurants and bars, making it the perfect spot for a night out. 

8. Visit the Roman Forum: As another ancient landmark, the Roman Forum was the center of political and social life in ancient Rome and is a fascinating spot to explore.
```

This effectively hits the nail on the head. More general recommendations are going to be exactly correct and avoid all of the pitfalls of incorrect AI knowledge.

As a general rule of thumb, it's best to leverage many automated tools as something that gets you 80% there. Some rough edges will (hopefully) need to be cleaned up for the foreseeable future. Otherwise, I'm out of a job

