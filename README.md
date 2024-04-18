# BlazorQuantityPicker

A simple quantitypicker that can be used to call an eventcallback with an object that you specify with a quantity that was selected.
Basically, you send it an object, a "starting quantity", minimum and maximum values if you want, and when the user clicks a decrease or increase button, you receive an event 
with the selected quantity and the object involved (that you sent in earlier).

Useful in tables with dynamic content etc.
It aligns to the right of whatever container you put it in 'cos that's what I needed.

You can use it like this:

 <QuantityPicker CurrentValue="@CurrentQuantity" Item="@SomeObjectThatwillbeReturned" Minimum="1" ValueChanged="SetItemQuantity"></QuantityPicker>

the SetItemQuantity method should look something like this:

```
 protected async Task SetItemQuantity((object, int) values)
 {
     var returnObject = (YourObject)values.Item1;
     var quantity = (int)values.Item2;

     //use the values as you wish.
 }
