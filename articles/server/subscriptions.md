# Subscriptions

Notification Subscriptions are a way for users to choose how and when to send out a notification. The subscriptions can be set up to only send for failures, successes, when certain filters are matched, etc. They
are highly customizable from the method they are sent, to the template being used to present the information.

When on the the Subscriptions page, the table of created subscriptions will be visible. From here subscriptions can be edited or deleted. Users can also see the execution results by viewing the subscriptions history. 

### Creating a Subscription

To create our first Subscription, click the green plus button in the top right corner of the Subscription table.
This will bring us to the create subscription page.

First, name the subscription something meaningful. Then be sure to enable the subscription by checking the enable option.
Next, we need to choose the event type that will trigger the notification. 

__Event Types :__
* LegiTest.LegiTestObjectFailed - This will trigger for any test or test group that has failed. 
* LegiTest.LegiTestObjectPassed - This will trigger for any test or test group that has passed.
* LegiTest.LegiTestExecutionFailed - This will trigger if the assembly ran into any issue executing the tests via the test runner.


Next, we can define any filters. If filters are added, then the notification will only be sent for test objects that match the defined filters.
For more info on how to use the filters, visit the [Notification Filters](notificationFilters.md) page.

After setting filters, we now select a notification target, either standard or custom, and a message template to use to format the data. Now, the subscription can be tested. Clicking the test button will fire the notification with the schema example data, and the test pop
up gives the option to apply filters or not. Once the notification is tested and working, save it, and it will now appear on the Subscription table on the subscription page.