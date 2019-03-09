# Ultimate-PreLoader-Guide
A comprehensive guide to Javascript Pre-Loaders




Preloaders are everywhere and have become an important part of a website’s design. They provide the visitors important feedback as the website loads. It informs them  that a process is in works and most importantly keeps them engaged. Overall a website is considered professional if it has a preloader. 
Technically Preloaders are basically small animations that plays in a loop for a while as the contents of the website loads. Eventually the preloader fades out to revel the website.  

There are multiple ways to  implement a preloader here are few of them:

# 1. JQuery (simple method)


The HTML creates 2 divs before the rest of the page. 

HTML:

	<div class="mask">	
		
			<div class="preloader">
			</div>	
		
	</div>
	


The CSS sets up the 2 divs with basic attributes. these attributes would be manipulated with the javascript events. In this kind of method a .gif file is used and played in a loop for few seconds.  

CSS:

     .preloader {
             position: absolute;
             top: 0;
             left: 0;
             width: 100%;
             height: 100%;
             z-index: 9999;
             background-image: url('loader.gif');
             background-repeat: no-repeat; 
             background-color: #FFF;
             background-position: center;
         }
   
     .mask{
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #fff;
            z-index: 99;	
       }
       
	
Here JQuery methods are used. The event is triggered when all the contents of the page is loaded.  

Javascript:

	<script>

		$(window).load(function() {
			$('.preloader').delay(400).fadeOut('slow');
			  $('.mask').delay(300).fadeOut('slow'); 
			$('body').delay(300).css({'overflow':'visible'});
		  });
           
	</script>


The ('.preloader') function is triggered first. It was important to include the ('.mask') attribute. As it prevents errors common error that arises when the user reloads the page from a lower section of the website. Thus it's important to create a white div which slowly fades out as soon as the pre loader is done. This provides a safety div between the preloader and the actual website and makes the transition smooth. 

This method of using a Pre-Loader is simple and easy but not much dynamic.





# 2. SVG





