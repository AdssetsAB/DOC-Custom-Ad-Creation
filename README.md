# How to create custom ads to be used in ACM

* [How to add custom events to ads](#1)
* [How to add input parameters to ads](#2)


# <a name="1"></a>How to add custom events to ads

In order to trigger **events** from the Ad and get the engagement mesure triggered derived from that events excute the following steps.

1. Get the code of your Ad:

``` html
<html>
<head></head>
<body>
AD Sample:
<b>Message</b>
<button onclick="sendAction()">Action</button>
<button onclick="sendAction2()">Action2</button>
<button onclick="sendClick()">Click</button>

<script>

    function sendAction(){
        console.log("Action");
    }

    function sendAction2(){
        console.log("Action2");
    }

    function sendClick(){
        console.log("Click");
    }

</script>

</body>
</html>

```

2. On the javascript part of your html Ad where the **actions** in your Ad should trigger the **events** place the text _"\_\_adsscore_event\_<name\_of\_event>\_\_";_ like in the example. (Optionaly you can also use the text )
This text will be replaced with a code that will send a message to the tracking code outside the iframe that to register the event.

``` javascript
    function sendAction(){
        "__adsscore_event_Action__";
        console.log("Action");
    }

    function sendAction2(){
        "__adsscore_event_Action2__";
        console.log("Action2");
    }

    function sendClick(){
        "__adsscore_event_click__";
        console.log("Click");
    }
```

3. Test your modifications by using the testing page [TestAd.html](./TestAd.html) page to test the text replacing and that events are correctly sent to the tracking part.

4. Send the html file to Adssets production team so they can create the single Ad or the Template so you can use it in ACM.

# <a name="2"></a>How to add input parameters to ads

In order to add inputs to parametrise your Ad excute the following steps.

1. Get the code of your Ad:

``` html
<html>
<head></head>
<body>
AD Sample: <br/>
<b>My text</b> <br/>

</body>
</html>

```

2. On wherever in your code you want to inject a value comming from an input, add the following place the text with the following syntax _\_\_adsscore\_input\<type\_input>\_<name\_of\_input>\_<default\_value>\_\__.
The types allowed are text, image and url at the moment. 
The names of input allowed should not be longer than 10 characters and contain only alphanumeric characters and blank spaces.
The default value allowed should not be longer than 80 characters and not contain the character _ without escaping. Ex. use "\_" instead of "_".
 

This text will be replaced with the value coming from the input in ACM. And the default value will be placed as default value for the input in ACM.

``` html
<html>
<head></head>
<body>
AD Sample: <br/>
<b>__adsscore_input_text_Message_My text__</b> <br/>

</body>
</html>
```

3. Test your modifications by using the testing page [TestAd.html](./TestAd.html) page to test the text replacing is working correctly with you specifications. In this case the Ad should display the specified defalt value.

4. Send the html file to Adssets production team so they can create the single Ad or the Template so you can use it in ACM.
