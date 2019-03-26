# ECF Network Website

This is a Hugo-based website: https://gohugo.io


# Content Management

## Taxonomy

The ecf.network website structure is based on this taxonomy:

* Home
* Members
* Community
* Grants?
* Projects?
  
## Home Page



# Developer Info

This section contains information for helping with the development of this site.

## Important Links

* Hugo Content Management: https://gohugo.io/content-management/organization/
* This is the Hugo theme that was copied and modified: https://github.com/jugglerx/hugo-hero-theme
* Bootstrap: https://getbootstrap.com/docs/4.0/utilities/spacing/ 

CSS gradients
* https://mycolor.space/gradient
* https://cssgradient.io/


## Development in Hugo

### Adding a new section

0. In the config.toml file, add a menu entry for the new section. This will create a menu item in the top nav.

	```
	[[menu.main]]
	identifier = "members"
	name = "Members"
	url = "/members/"
	weight = 3	
	```
1. Create a new folder in /content with the name of the new section (all lowercase, no spaces). 
		* Create an _index.md file in that folder. It is convenient to copy the contents of a similar file in a sibling folder.
2. In the /layouts folder, clone an existing folder that roughly matches the desired layout. 
		* You will need to edit the contents of these files to be match the name of the new section. 
3. In the /assets/scss/pages folder, clone an existing folder that has the styles needed for the layouts folder that you cloned in the previous step.
		* Edit the scss files in this folder and find-replace the css class names to match the new section.
4. In the file /themes/hero/assets/scss/style.scss, you need to add an entry for each new SCSS file added in the previous step. 
		* For example, the following is the SCSS import for members-summary, which maps to the file /layouts/members/summary.html
	
	```	
		@import 'pages/members/members-summary';
	```

### Adding and Choosing Fonts

* To add a new webfont, edit the file: /themes/hero/assets/scss/style.scss
	* Add a the link to the webfont like this:
	
	```
	@import url('https://fonts.googleapis.com/css?family=Lato:400|Open+Sans:400,700');
	```
* Next, edit the file: /themes/hero/assets/scss/_bootstrap-variables.scss
	* Add/replace the font name in the appropriate entry: 
	
	```
	$font-family-base: 'Open Sans', 'Helvetica Neue', Arial, sans-serif,
	  -apple-system;
	$font-family-heading: 'Lato', 'Helvetica Neue', Arial, sans-serif, -apple-system;
	```



