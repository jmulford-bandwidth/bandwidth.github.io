<div id="hero">
  <h1>Add phone calling and text messaging to your app.</h1>
  <p>Ready to bring your ideas to life? It's pretty easy. See how it's done using the examples below,<span class="remove4mobile"><br></span> or jump right in to the full <a href="http://dev.bandwidth.com/ap-docs/methods/restApi.html">API reference.</a></p><br>
  <div id="smscard" class="devCards sms active">
    <h2><i class="icons8-sms" style="font-size: 21px"></i> Messaging</h2>
    <span class="remove4mobile">Send a text. It is really simple! SMS or MMS, send it now.
    <br><br></span><button class="iconic-button iconic-small" id="smsexpand"><i class="icons8-expand-arrow"></i></button><a href="/howto/sendSMSMMS.html" class="aimg"><button class="fulltut medium" id="smsfulltut" disabled>Full Tutorial</button></a>
  </div><div id="voicecard" class="devCards voice">
    <h2><i class="icons8-phone" style="font-size: 17px"></i> Voice</h2>
    <span class="remove4mobile">Wondering how to make a call? Put that number to use!
    <br><br></span><button class="iconic-button iconic-small" id="voiceexpand"><i class="icons8-expand-arrow"></i></button><a href="/howto/outboundCall.html" class="aimg"><button class="fulltut medium" id="voicefulltut" disabled>Full Tutorial</button></a>
  </div><div id="pncard"class="devCards pn">
    <h2><i class="icons8-hashtag" style="font-size: 21px"></i> Phone Numbers</h2>
    <span class="remove4mobile">Learn how to get a telephone number. You will need to do this first. Go for it!
    <br><br></span><button class="iconic-button iconic-small" id="pnexpand"><i class="icons8-expand-arrow"></i></button><a href="/howto/buytn.html" class="aimg"><button class="fulltut medium" id="pnfulltut" disabled>Full Tutorial</button></a>
  </div>
</div>

<div class="languageselector">
      <div class="radio-group clearfix">
          <input type="radio" name="basic-options" value="four" id="radio-four" class="lang-curl trigger" data-rel="lang-curl" checked />
          <label for="radio-four"><span>curl</span></label>
          <input type="radio" name="basic-options" value="one" id="radio-one" class="lang-js trigger" data-rel="lang-js"/>
          <label for="radio-one"><span>js</span></label>
          <input type="radio" name="basic-options" value="two" id="radio-two" class="lang-csharp trigger" data-rel="lang-csharp"/>
          <label for="radio-two"><span>c#</span></label>
          <input type="radio" name="basic-options" value="three" id="radio-three" class="lang-ruby trigger" data-rel="lang-ruby"/>
          <label for="radio-three"><span>ruby</span></label>
      </div>
   </div>

<div class="divider"></div>

### Send a message

```js
client.Message.send({
    from : "+19195551212",
    to   : "+19195551213",
    text : "Thank you for susbcribing to Unicorn Enterprises!"
})
.then(function(message){
    console.log(message.id);
});
```

```csharp
var message = await client.Message.SendAsync(new MessageData {
    From = "+19195551212",
    To = "+19195551213",
    Text = "Thank you for susbcribing to Unicorn Enterprises!"
});
```

```ruby
message = Message.create(client, {
    :from => "+19195551212",
    :to => "+19195551213",
    :text => "Thank you for susbcribing to Unicorn Enterprises!"
})
```

```curl
curl -v -X POST https://api.catapult.inetwork.com/v1/users/{userId}/ \
    -u {token}:{secret} \
    -H "Content-type: application/json" \
        -d \
    '
    {
        "from": "{fromNumber}",
        "to": "{toNumber}",
        "text": "Good morning, this is a test message",
        "callbackUrl": "http://my.callback.url"
    }'
```

### Make a call

```js
client.Call.create({
    from: "{fromNumber}",
    to: "{toNumber}"
})
.then(function (call) {
    console.log(call.id);
})
```

```csharp
var call = await client.Call.CreateAsync(new CreateCallData{
    From = "{fromNumber}",
    To = "{toNumber}"
});
```

```ruby
call = Call.create(client, {:from => "{fromNumber}", :to => "{toNumber}"})
```

```curl
curl -v -X POST https://api.catapult.inetwork.com/v1/users/{userId}/calls \
    -u {token}:{secret} \
    -H "Content-type: application/json" \
    -d \
    '
    {
        "from": "{fromNumber}",
        "to": "{toNumber}"
    }'
```

### Buy a telephone number

```curl
curl -v -X GET  https://api.catapult.inetwork.com/v1/availableNumbers/local?city=Cary&state=NC&pattern=*2%3F9*&quantity=2 \
  -u {token}:{secret} \
  -H "Content-type: application/json" \
```

```js
// Search available local phone numbers with area code 910

// Promise
client.AvailableNumber.search("local", { areaCode : "910", quantity : 1 })
.then(function (numbers) {
    return client.PhoneNumber.create({
        number: numbers[0].number,
        name: "My 910 Number",
        applicationId: "a-1234"
    });
})
.then(function (number) {
    console.log(number.id);
});
```

```csharp
var results = await client.AvailableNumber.SearchLocalAsync(new LocalNumberQuery{ AreaCode = "910", Quantity = 1});
var number = await client.PhoneNumber.CreateAsync(new CreatePhoneNumberData {
    Number = results[0].number,
    Name = "My 910 Number",
    ApplicationId = "a-1234"
});
```

```ruby
results = AvailableNumber.search_local(client, {:area_code => "910", :quantity => 1})
puts("Found numbers: #{(numbers.map {|n| n[:number]}).join(', ')}")
number = PhoneNumber.create(client, {:number => numbers[0][:number]})
puts("Now you are owner of number #{number.number} (id #{number.id})")
```

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
<script>
$(document).ready(function landing(){

  if ($(window).width() >= 980) {
  // Adding classes for sms, voice and pns
  $('#send-a-message').nextUntil('h3').addClass('smstut');
  $('#send-a-message').addClass('smstut');
  $('#make-a-call').nextUntil('h3').addClass('voicetut');
  $('#make-a-call').addClass('voicetut');
  $('#buy-a-telephone-number').nextUntil('h3').addClass('pntut');
  $('#buy-a-telephone-number').addClass('pntut');

  // Access to parent div on this page only
  $('#hero').parent().addClass('landingpage');

  // Setting default language
  $('.lang-curl').parent().addClass('active');

  // Toggle between languages
  $('code').not('.lang-curl').parent().hide();
  $('.trigger').click(function() {
      $('code').parent().removeClass('active');
      $('.' + $(this).data('rel')).parent().addClass('active');

      if ($('#voicecard').hasClass('active')){
        $('pre').hide();
        $('.voicetut.active').show();
      }
      if ($('#smscard').hasClass('active')){
        $('pre').hide();
        $('.smstut.active').show();
      } else if ($('#pncard').hasClass('active')){
        $('pre').hide();
        $('.pntut.active').show();
      }
  });

  // Showing proper code sample or sms, voice and pns
  var tuts = $('.voicetut, .smstut, .pntut');

  tuts.hide();

  // Disable buttons on cards that are inactive
  $('.devCards.active').find('.fulltut').prop("disabled",false);

  $('#smsexpand').click(function(){
      $('pre').hide();
      $('.smstut.active').show();
      $('.devCards').removeClass('active');
      $(this).parent().addClass('active');
      $('.devCards').find('.fulltut').prop("disabled",true);
      $('.devCards.active').find('.fulltut').prop("disabled",false);
  });
  $('#voiceexpand').click(function(){
      $('pre').hide();
      $('.voicetut.active').show();
      $('.devCards').removeClass('active');
      $(this).parent().addClass('active');
      $('.devCards').find('.fulltut').prop("disabled",true);
      $('.devCards.active').find('.fulltut').prop("disabled",false);
  });

  $('#pnexpand').click(function(){
      $('pre').hide();
      $('.pntut.active').show();
      $('.devCards').removeClass('active');
      $(this).parent().addClass('active');
      $('.devCards').find('.fulltut').prop("disabled",true);
      $('.devCards.active').find('.fulltut').prop("disabled",false);
  });
  $('.smstut.active').show();
  } else {
    // Adding classes for sms, voice and pns
    $('#send-a-message').nextUntil('h3').addClass('smstut');
    $('#send-a-message').addClass('smstut');
    $('#make-a-call').nextUntil('h3').addClass('voicetut');
    $('#make-a-call').addClass('voicetut');
    $('#buy-a-telephone-number').nextUntil('h3').addClass('pntut');
    $('#buy-a-telephone-number').addClass('pntut');

    // Access to parent div on this page only
    $('#hero').parent().addClass('landingpage');

    // Setting default language
    $('.lang-curl').parent().addClass('active');

    // Toggle between languages
    $('code').not('.lang-curl').parent().hide();
    $('.trigger').click(function() {
        $('code').parent().removeClass('active');
        $('.' + $(this).data('rel')).parent().addClass('active');

        if ($('#voicecard').hasClass('active')){
          $('pre').hide();
          $('.voicetut.active').show();
        }
        if ($('#smscard').hasClass('active')){
          $('pre').hide();
          $('.smstut.active').show();
        } else if ($('#pncard').hasClass('active')){
          $('pre').hide();
          $('.pntut.active').show();
        }
    });

    // Showing proper code sample or sms, voice and pns
    var tuts = $('.voicetut, .smstut, .pntut');

    tuts.hide();

    // Disable buttons on cards that are inactive
    $('.devCards.active').find('.fulltut').prop("disabled",false);

    $('#smscard').click(function(){
        $('pre').hide();
        $('.smstut.active').show();
        $('.devCards').removeClass('active');
        $(this).addClass('active');
        $('.devCards').find('.fulltut').prop("disabled",true);
        $('.devCards.active').find('.fulltut').prop("disabled",false);
    });
    $('#voicecard').click(function(){
        $('pre').hide();
        $('.voicetut.active').show();
        $('.devCards').removeClass('active');
        $(this).addClass('active');
        $('.devCards').find('.fulltut').prop("disabled",true);
        $('.devCards.active').find('.fulltut').prop("disabled",false);
    });

    $('#pncard').click(function(){
        $('pre').hide();
        $('.pntut.active').show();
        $('.devCards').removeClass('active');
        $(this).addClass('active');
        $('.devCards').find('.fulltut').prop("disabled",true);
        $('.devCards.active').find('.fulltut').prop("disabled",false);
    });
    $('.smstut.active').show();
  }
});
$(window).resize(landing);
</script>