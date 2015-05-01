# Zen Store Locator Integration

The following documentation applies to [Zen Store Locator](https://zenstorelocator.com/) service.

## Creating custom forms

Odds are your store locator does not show up on your homepage, but has its own separate page. However, for convenience, you might have a zip code input field somewhere in your menu for users to type in their address and be redirected to a store locator.

### Custom address form:

You can implement a simple form easily with Zen Store Locator:

1. First, create a form where user will type in their zip code.
	
	```html
	<form method="get" action="https://zenstorelocator.com">
		<label for="zip">Zip code:</label>
		<input name="address" type="text" id="zip" placeholder="please enter zipcode" />
		<button>Search</button>
	</form>
	```
	
	We are using `https://zenstorelocator.com` as an example; in your own form you would replace this with a URL of where *your own store locator is hosted* on your site.
	
	You can see that we have one label and one `address` field. The address field is the one we will redirect to the store locator.
	
	**Note:** In practice it doesn't even have to be a zip code, it can be any type of address: city, state, region or even a country.
	
2. Insert the form wherever you want it to appear on your site. This is an unstyled form, but the end result will look something like this:
	
	![Custom form - example](https://raw.githubusercontent.com/zenstorelocator/integration/master/img/custom-form-example-1.png)
	
### Passing in filter features:

todo