# Zen Store Locator Integration

The following documentation describes form integration options with your [store locator](https://zenstorelocator.com/).

## Demo

Check out the [custom form demo](http://zenstorelocator.github.io/demo/custom-form/) here.

## Creating custom forms

Odds are your store locator does not show up on your homepage, but has its own separate page. However, for convenience, you might have a zip code input field somewhere in your menu for users to type in their address and be redirected to a store locator.

That way your users can be looking at the stores directly relevant to them. You can implement one the following way:

### Custom address form:

The simplest way is to create a custom form that passes an `address` field to Zen Store Locator:

1. First, create a form where user will type in their zip code ([full html file here](https://github.com/zenstorelocator/integration/blob/master/examples/custom-form-simple.html)):
	
	```html
	<form method="get" action="https://zenstorelocator.com">
		<label for="zip">Zip code:</label>
		<input name="address" type="text" id="zip" placeholder="please enter zipcode" />
		<button>Search</button>
	</form>
	```
	
	We are using `https://zenstorelocator.com` as an example; in your own form you would replace this URL with a URL of where *your own store locator is hosted* on your site (for example `http://example.com/store-locator`).
	
	The only input field on this form is named `address`. This is where the user will type in their zip code and what we will pass to the locator.
	
	**Hint:** In reality it doesn't even have to be limited to zip code only. It can be any type of recognizable address: a street, city, state or a region.
	
2. Insert the form wherever you want it to appear on your site. This is an unstyled version, but the end result will look something like this:
	
	![Custom form - example](https://raw.githubusercontent.com/zenstorelocator/integration/master/img/custom-form-example-1.png)
	
	Now your users can pass an address and be taken directly to that location on the map.
	
### Extending with filter:

If you have filter enabled on your account, you can also let your users pre-select what stores to search for:

1. Create a form with whatever filter parameters you have ([full html file here](https://github.com/zenstorelocator/integration/blob/master/examples/custom-form-with-filter.html)):
	
	```html
	<form method="get" action="https://zenstorelocator.com">
		<p>
			<label for="zip">Zip code:</label>
			<input name="address" type="text" id="zip" placeholder="please enter zipcode" />
		</p>
		<p>
			<span>Only locations with:</span>
			<br/>
			<label>
				<input type="checkbox" name="filter[]" value="Sirena Espresso Machine" />
				<span>Sirena Espresso Machine</span>
			</label>
			<br/>
			<label>
				<input type="checkbox" name="filter[]" value="Clover Crafted Small Batch Coffee" />
				<span>Clover Crafted Small Batch Coffee</span>
			</label>
		</p>
		<p>
			<button>Search</button>
		</p>
	</form>
	```
	
	In this example we are giving two options. A user can search for stores that have **Sirena Espresso Machine** or **Clover Crafted Small Batch Coffee**.
	
2. Note that the filter input has brackets inside the **name** attribute: `name="filter[]"`
	
	The **value** attribute has to match the name of your feature **_exactly_** as it is filled out in [your dashboard](https://zenstorelocator.com/filter).
	
3. The form will now look like this (users can check one or several filters and your locator will adjust the search accordingly):
	
	![Custom form - example](https://raw.githubusercontent.com/zenstorelocator/integration/master/img/custom-form-example-2.png)
	
## Notes:

1. It is important that the address field is always named `address`, and filter as `filter[]`. Both of these parameters are optional.
2. Make sure the form has `method="get"` and is pointing to the correct store locator page on your site.

## Something else?

Can you think of other parameters you'd like to pass to your locator? Give us a shout at [support@zenstorelocator.com](mailto:support@zenstorelocator.com?subject=Integration)