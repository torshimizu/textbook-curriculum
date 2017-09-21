# HTML Forms
## Learning Goals
- Discover the mechanisms in the HTML standard that allow for interactive elements on a website
- Discuss how to create accessible and semantic forms
- Make and _post_ our first HTML form!

Forms are how users provide input to servers for operation. Everything from authoring a tweet to logging into an email account is accomplished using a small set of HTML tags that create and structure forms.

## Relevant Tags
- `<form>`
- `<fieldset>` and `<legend>` (handy, but not often used)
- `<label>`
- `<input>`
  - `<input type="text">`
  - `<input type="checkbox">`
  - `<input type="radio">`
  - `<input type="password">`
  - `<input type="submit">`
  - `<input type="hidden">`
- `<textarea>`
- `<select>`
  - `<option>`
- `<button>`, and `<input type="button">` (primarily used for JavaScript interactions)

## Creating and Submitting Forms
Forms are used to create requests to servers that can create, update, and delete resources.

We are going to look at how inputs from a form are passed along through the browser to our server. Let's open the web application we have been using and create a new route and view like:

```bash
$ touch app/views/books/new.html.erb
```

```ruby
# app/controllers/books_controller.rb
def new

end
```

Then, let's open the view (`app/views/books/new.html.erb`) in our editor. Add the following code to the page:

```html
<form action="/books" method="post" accept-charset="utf-8">
  <!-- SPECIAL INPUT TO ALLOW RAILS TO USE THIS FORM -->
  <input name="authenticity_token" value="<%= form_authenticity_token %>" type="hidden">


  <label for="title">Title</label>
  <input type="text" name="title" value="" id="title">

  <label for="author">Author</label>
  <input type="text" name="author" value="" id="author">

  <input type="submit" value="Submit">
</form>
```

In the `form` tag, the `action` attribute defines to which route this form will `POST`. We're using the route that corresponds to the RESTful POST route for creating a new entry. We know that submitting the form will create a `POST` request because that's the value of the `method` parameter. We could use `PUT`, `DELETE`, or any other verb (even `GET`, but that's kinda silly).

Next we have a `label` tag
```html
<label for="title">Title</label>
```

Labels are the text portion of a form. The reason we use labels instead of plain text is because we can join an `input` and a `label` to when the text is clicked the cursor will focus on the input. The `for` attribute defines the `id` that the `label` will match. Also, creating a link between the `label` and `input` tags is critical in creating usable form content for folks using screen readers.

Next we have two `input` tags with the type of 'text' (see [here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) for all input info).

```html
<input type="text" name="title" value="" id="title">
<input type="text" name="author" value="" id="author">
```

Each `input` tag will pass a value along to the server when we submit the form. The data passed to the web server in our _POST request_ is collected in a Ruby hash called `params`. In this hash, the `name` attribute of the HTML `<input>` defines the key, and the user input is value. In this case `username` will be assigned to what we type into the first text field.

And finally we have an `input` with the type of _submit_. This input creates a button to click that will send an HTTP request with the form data to the route in the `action` attribute of the `form` tag.

Give it a try. It broke, right? We haven't taught our app how to make this work!


### Make it Work

When we push submit, a request is made to POST '/books/create'. That request maps to the create method of the Books controller. So we need to put code in that method to save a new book based on the user input from the form.

Here is an example of how we would do that. Take a minute to observe what is going on. What is familiar and what is new?

```ruby
#books_controller.rb

  def create
    book = Book.new(
      title: params[:title],
      author: params[:author]
    )

    book.save

    redirect_to(book_path(book.id)
  end
```

First, we are creating a local variable to store a new instance of book. We are using a local variable because we are not going to pass that variable to a view. It is only ever going to be used in this method. 

When we make the new instance of Book, we setting two attributes, title and author. In order to set those attributes to

The params hash will always contain data from a form where the keys will be made from the values of the 'name' attributes of the input fields. The values of those keys are the user input.

At the end, instead of creating a new page for this action, we can redirect it to another path. After creating a new record of a resource, like book, it's common to redirect to that new record's show page.


Create the file.
```bash
$ touch app/views/books/show.html.erb
```

Create the show method, in `books_controller.rb`, that will find the book by the id we pass in the url. The id is accessible through the params hash.

```ruby
#books_controller.rb

  def show
    @book = Book.find(params[:id])
  end
```


```html
<!-- app/views/books/show.html.erb -->

<h2> <%= @book.title %> </h2>
<h3> <%= @book.author %> </h3>
<p> <%= @book.description %> </p>

```
