---
layout: post
title: Hackaboom!
---
I was at my first hackathon, [Hackaboom](https://twitter.com/zeplin_tr), last weekend with a team of friends. Decided to write a little bit about it.
This picture was taken after the event. We might look a bit sleepy.
![team.jpg](\images\blog\hackaboom\team.jpg "team.jpg")
<!--break-->
Before anything about the hackathon, I just want to say that I am still planning to do that post about Tough Walk. The game had many iteration since the jam and I could not find time to work on it or make a post about it. It is on the way though, I promise.

With this out of the way, let me tell you about the hackathon.

### The idea

The theme was making something that will help your favorite superhero. But as a team we had no superhero genre fans. So we just picked a hero based on the ideas we came up with.
Which was a character I knew nothing about before. Never read or watched X-Men properly. Anyway, [Cyclops](https://en.wikipedia.org/wiki/Cyclops_(Marvel_Comics)) was our pick. If you do not know the hero, it would make more sense if you read a bit about him.
We decided to make him be able to hit faraway targets by upgrading his glasses. This glasses would have a high tech camera on them. Using the data from the glasses an AR interface would help him aim and hit targets which he could not see with his eyes. In theory, this would work with a villain face recognition database. But for the hackhatone prototype we replaced face recognition with AR marker recognition, and the AR glasses with a mobile phone.

### The final product (AR side)
Here is a little video from the AR end of the final product to make it clear.

<iframe width="560" height="315" src="https://www.youtube.com/embed/usNv0fYOb-w" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

A crosshair appears when a villain(A person with an AR marker.) enters to the line of sight. Just by looking at the crosshair, cyclops would be able to aim at a target since he is sending out light beams. When the crosshair overlaps with the point the user is looking (middle of the screen) it turns green, indicating a possible hit. It also shows some info about the villain, which can be updated by VillainDB interface on real time.
### The final product (Database side)
This is the VillainDB, a list of all known villains.
![villainDB.png](\images\blog\hackaboom\villainDB.png "villainDB.png")
One can add, remove, change details about villains at any time they want. This data is sent to backend, which in turn updates the data shown on the AR side. So in theory, whenever someone at the HQ learns about a new villain, they can add update the database and let Cyclops' glasses start searchin for that villain too.

I tried to keep the technical explanation part short, and skipped the details about the database. Partly because I only have a vague idea about how those parts work. So, me trying to explain what others did would be a bit disrespectful, I think. Which was actually what I really loved about this event. As a team, we managed to share the work in such a way that we were able to focus on our part without being distracted by the work of others. I will also introduce the team, alongside with the work we did on the project.

### The team
Mahmut was the experienced hackathon participant among us. He usually lead the team and worked on the backend side of the database.
Halit was the crazy programmer of the event. (He did not sleep for the entire hackathon. For real.) He worked on the frontend side of the database.
And I was the guy who cannot make anything for mobile unless it is made with Unity. So I coded the AR interface.
Meltem worked on anything else we had to deal with as a team. Like preparing slides, collecting the data for the database and making design templates for the interfaces.

### What went right
- Sharing the work between the team. I just explained this so moving on.
- The idea. Not as in *We found the greatest idea!*. Everybody in the team liked the idea we came up with, so we were really motivated fot the entire event.
- Making a finished product. At the end of the event everything was up and running(except for a little mishap). All interactions between the different parts of the project were working. On an accelerated development event like this, I consider this to be an important achievement.

### What went wrong
- Time management. We finished things just in time but we had a very little time to work on things like the slides and videos for the presentation. This caused a real stress to as at the end of the event. I think this was mostly because 3 people in our team had no prior hackathon experience. 
- Presentation. Because of the reason given above, we could not prepare for the presentation. It was really improv on scene, so it did not go well enough.
- Not double checking the system. As it turned out there was a little bug in the system which prevented us from updating the villain info real time. So when the judges were checking our app, we could not demonstrate that part properly. This is totally on us for not trying it out while waiting for the judges to arrive. The fix took Halit like 3 minutes after realizing the problem.

I want to thank Zeplin for the venue. Food and snacks were wonderful. Place was really comfortable. I can say that I will participate in any upcoming Zeplin event without thinking twice.

I personally did not go to the event to win a prize, though it would be great. We had the same thought as a team as far as I know. This event had prizes for the top 4 teams picked by the judges. But to our surprise, they decided to add a few special jury prizes to the mix. One them was given to us under the name "Fullest Stack". They said they were impressed by the usage of different technologies/frameworks in our project. Personally, it felt great to have a prize. And also it showed how much thay cared about the participants. They actually made new prize tiers for people they thought who deserved a prize.

In general, it was a great experience participating in an event like this. And I will spend more time on tech community events like this later on, hopefully. It was also nice to feel that time constraint again after a few months. Ludum Dare in on the horizon, and I should be mentally ready for it when the time comes. I just want to thank everyone in our team as I am closing.

See you on another post!