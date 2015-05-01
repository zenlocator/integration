# Zen Store Locator Integration

The following documentation applies to [Zen Store Locator](https://zenstorelocator.com/) service.

## Creating custom forms

Odds are your store locator does not show up on your homepage, but has its own separate page. However, for convenience, you might have a zip code input field somewhere in your menu for users to type in their address and be redirected to a store locator.

That way your users can be looking at the stores directly relevant to them.

### Custom address form:

The simplest way is to create a custom form that passes an `address` field to Zen Store Locator:

1. First, create a form where user will type in their zip code:
	
	```html
	<form method="get" action="https://zenstorelocator.com">
		<label for="zip">Zip code:</label>
		<input name="address" type="text" id="zip" placeholder="please enter zipcode" />
		<button>Search</button>
	</form>
	```
	
	We are using `https://zenstorelocator.com` as an example; in your own form you would replace this URL with a URL of where *your own store locator is hosted* on your site (for example `http://example.com/store-locator`).
	
	The only input field on the form is an `address`. This is the field we will pass to the locator.
	
	**Note:** In reality it doesn't even have to be a zip code. A user can type in a street, city, state or even a country.
	
2. Insert the form wherever you want it to appear on your site. This is an unstyled form, but the end result will look something like this:
	
	![Custom form - example](https://raw.githubusercontent.com/zenstorelocator/integration/master/img/custom-form-example-1.png)
	
### Passing in filter features:

If you have filter enabled on your account, you can also pass in features to your locator. This will pre-set a locator on the specified address **and** pre-set the filter:

1. Create a form:
	
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
	
	Now the form is expanded a bit to include a `filter[]` parameter.
	
2. Note that the filter input has brackets inside the **name** attribute: `filter[]`.
	
	The **value** attribute has to match the name of your feature exactly as it is filled out in [your dashboard](https://zenstorelocator.com/filter).
	
3. The form will now look like this. The user can check one or several filters and your locator will adjust the search accordingly.
	
	![Custom form - example](https://raw.githubusercontent.com/zenstorelocator/integration/master/img/custom-form-example-2.png)
	
### Notes:

1. It is important that the address field is always named `address`, and filter as `filter[]`. Both of these parameters are optional.
2. Make sure your form has `method="get"` and is pointing to your store locator page.

	