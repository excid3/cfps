✅ Accepted

**Title**

_Publicly viewable title. Ideally catchy, interesting, essence of the talk. Limited to 60 characters._

Advanced ActionText: Attaching any model in rich text

**Abstract**

_A concise, engaging description for the public program. Limited to 600 characters._

Whether it's @ mentions for users, hashtags, or other resources, many application these days need rich text fields. ActionText allows you to embed rich snippets for any model in your Rails app, but it requires a bit of communication with the backend. We'll explore how to add @ mentions for users and YouTube embeds to take advantage of ActionText attachments and see how it works.

**Details** 

_Include any pertinent details such as outlines, outcomes or intended audience._

The intended audience for this talk is anyone who hasn't used ActionText before (ie. most of the Rails community).

A rough outline for the talk is:

- What is ActionText?
  - How do I use it?
  - Uploading images works out of the box
- How does ActionText work?
  - It's based around a concept of Attachments
  - On the client side, it uses the Trix editor
  - On the server side
    - You add `has_rich_text :body` to add the field
    - It stores the `body` in an ActionText attachment model
- Advanced ActionText
  - You can use ActionText to embed any type of attachments
    - An example of this is @ mentions for users inline
    - YouTube videos
    - Tweets
  - Attachments are identified by signed global IDs
  - This prevents tampering, but also a way to look up associated records
  - Every attachment has two templates it renders depending on the context
    - Trix editor template
    - Regular template
  - Adding custom attachments
    - Add your hook into Trix
    - Add a Rails endpoint that returns the signed global ID and template
    - Insert into Trix
  - Examples
    - @ mentions for users
      - Adding Tribute to Trix for listening to "@"
      - Adding endpoint in Rails to lookup users
      - Inserting user attachment
    - YouTube embeds
      - Extending Trix's link form to match agains YouTube URLs
      - Adding endpoint in Rails to lookup YouTube video
      - Inserting video thumbnail preview
      - Rendering actual video embed

**Pitch**

*Explain why this talk should be considered and what makes you qualified to speak on the topic.*

ActionText is a core feature of Rails that launched without much fanfare and I want to give this talk to bring more attention to it. I'd venture to guess 80% or more of Rails devs have wanted to implement a nice, rich text field in their applications and don't realize they can now do this with a core Rails feature.

I'd say I'm uniquely qualified to give this talk because I spent several weeks after ActionText was released learning how it works and talking with George on the Rails core team to learn how to implement custom attachments. I have covered it in a screencast and left notes in the GitHub issues to help anyone interested in using ActionText more. I also added the rich_text field generator to the Rails scaffold generator to make it easier to use this feature and plan on contributing these notes to the Rails guides.

**Bio**
Chris is the founder of GoRails, host of the Remote Ruby podcast, and creator of Jumpstart and Hatchbox.io. He loves building tools to make developers' lives easier and helping people learn to code.
