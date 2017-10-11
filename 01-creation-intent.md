Intents are the backbone of Dialogflow projects. Each intent describes a mapping between what a user says and what action should be taken by your software. In this step, we'll create an intent that will allow you to add new items to your todo list.

# Create a new intent

![](screenshots/01-creation-intent/01-create-intent.markedup.png)
- Navigate to the Intents page.
- Click on the "Create intent" button.

![](screenshots/01-creation-intent/...)
- Give your intent a name.
- In the "User says" section, add some expressions that you think people would use to create a new item. Here are some examples:
  - Create new item
  - New item
  - New todo
  - Make a new item
  - Create a todo
- Your examples don't have to be comprehensive: Dialogflow automatically combines aspects of the examples you provide to generate new ones. For example, given the examples above, Dialogflow will also invoke your new intent when the user says "Make new todo".

![](screenshots/01-creation-intent/...)
- Click on the quotation marks in the left of the "User says" input box. They should be replaced by an at symbol (@).
- You're now in template mode. Try entering these templates:
  - I want to create a new todo with text @sys.any:text
  - New todo @sys.any:text
  - Create item to @sys.any:text
- "@sys.any:text" should be highlighted in both examples. This means that, if a user enters "Make a new item to wash the dishes", the intent will be invoked with the parameter "text" set to "wash the dishes".
- You can see a list of the intent's parameters in the "Action" section. Right now, you only have one parameter: "text".

![](screenshots/01-creation-intent/...)
- Make the "text" parameter required by checking the checkbox in the leftmost column of the parameter table.

![](screenshots/01-creation-intent/...)
- Click on the "Define prompts" link in the rightmost column of the parameter table.

![](screenshots/01-creation-intent/...)
- Add a prompt for when the user doesn't provide any text for the todo, e.g. "What should the text of the new item be?"

![](screenshots/01-creation-intent/...)
- Click on the "Save" button.

# Set up webhook fulfillment for the intent

![](screenshots/01-creation-intent/...)
- Open the "Fulfillment" section of the intent editing page.
- Check the "Use webhook" checkbox.
- Navigate to the Fulfillment page. Don't forget to save your intent first!

![](screenshots/01-creation-intent/...)
- Insert code to create a new todo item and respond to the user on line 105 of the Inline Editor.

![](screenshots/01-creation-intent/...)
- Deploy your new code.

# Test the intent

![](screenshots/01-creation-intent/...)
- In the Actions for Google simulator, type or say "Talk to my test app", then create a new todo item using the intent you just created.

![](screenshots/01-creation-intent/...)
- Open the Firebase Console and navigate to the Database page.
- Check that the newly-created todo exists in the database.