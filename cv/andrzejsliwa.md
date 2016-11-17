<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
<script type='text/javascript'>
  $( document ).ready(function() {
    // clean up some dd's that don't have a p
    $("dd:not(:has('p'))").each(function(i, element) { 
      $(element).wrapInner('<p></p>');
    });

    $.getScript('./stats-ir.js', function() {
      article_stats = data[0]['stats']['articles'];

      $('a').each(function(i, element) { 

        var href = $(element)[0].getAttribute('href');
        if ($(element)[0].innerHTML.indexOf('doi.org') == 0 ) {
          $($(element)[0]).addClass('doiLink');
          var doi = $(element)[0].innerHTML;
          doi = doi.substr(doi.indexOf('/') + 1);  // strip out doi.org/ 
          $($(element)[0]).closest('dd').append('<div data-badge-popover="right" data-badge-type="2" data-doi="' + doi + '" data-hide-no-mentions="true" class="altmetric-embed"></div>');
            metrics = true;
        } else if (href.indexOf('scholar.google.com') > 0) {
          var gsid = href.substring(href.indexOf('cites=') + 6)
          for (var i=0; i<article_stats.length; i++) {
            if (article_stats[i][0].indexOf(gsid) > 0) {
              $($(element)[0]).closest('dd').append('<div class="google-scholar"><a href="' + href +'" ><img src="scholar_logo_long.png" align="left" /></a><span class="metricbubble">' + article_stats[i][1] + '</span></div>');
              $(element).remove()
            }
          }
        } 
      });  
    });

    $.getScript("https://d1bxh8uas1mnw7.cloudfront.net/assets/embed.js", function() {
        $('head').append('<link rel="stylesheet" href="./altmetric-overrides.css" type="text/css" />')
    });

    $('head').append('<link rel="stylesheet" href="genericons/genericons.css" type="text/css" />');

    // Do some link handling
    $("a").attr('target','_blank');

    // change links called "link" to icon
    $("a").filter(function() {
      return $(this).text() === "link";
    }).addClass("with-genericon").addClass("externalLink").attr('alt', 'link to open access version').text(' ');

    // change links called "video" to icon
    $("a").filter(function() {
      return $(this).text() === "video";
    }).addClass("with-genericon").addClass("videoLink").attr('alt', 'link to video').text(' ');

    // change links called "slides" to icon
    $("a").filter(function() {
      return $(this).text() === "slides";
    }).addClass("with-genericon").addClass("slidesLink").attr('alt', 'link to slides').attr('title', 'link to slides').text(' ');

    // change Twitter link to icon
    $("a").filter(function() {
      return $(this).text() === "Twitter";
    }).addClass("with-genericon").addClass("contant-icon").addClass("twitterLink").attr('alt', 'Twitter').attr('title', 'Twitter').text(' ');

    // change Github link to icon
    $("a").filter(function() {
      return $(this).text() === "Github";
    }).addClass("with-genericon").addClass("contant-icon").addClass("githubLink").attr('alt', 'Github').attr('title', 'Github').text(' ');

    // change Github link to icon
    $("a").filter(function() {
      return $(this).text() === "email";
    }).addClass("with-genericon").addClass("contant-icon").addClass("emailLink").attr('alt', 'email').attr('title', 'email').text(' ');    

  });
</script>



# Andrzej Lucjan Śliwa
## CTO / Technical Founder / Software Developer
[Twitter](https://twitter.com/andrzejsliwa)
[Github](https://github.com/andrzejsliwa)
[LinkedIn](https://pl.linkedin.com/in/sliwa)
[Email](mailto:andrzej.sliwa@i-tool.eu)

> [Download PDF](andrzejsliwa.pdf)

------

### Education {#education}

Master of Computer Science, Poznan University of Technology
: Computer Science Honours, Software Engineering
  __2009__

Bachelor of Computer Science, Information Technology Vocational College
: Computer Science Honours, Databases
  __2007__

------

### Professional Affiliations {#employment}

Chief Technology Officer
 : Mediteo GmbH   
 __2016 – present__
 
 : I redefined technical strategy of Mediteo by redesign and choosing more suitables architectures for server infrastructure, backend and mobile clients. Led Engineering, Product, Design and QA teams. 
   
   Built a distributed team of passion-driven professionals. Successfully applied Agile methodologies. 
   
   Encouraged team to build quality software by following Test Driven Development, Pair Programming, Domain Driven Design, CQRS and Event Sourcing. 
   
   Supported CEO at evolving the company’s mission, vision and goals to serve its customers as the best healthcare product provider, helping them to actively manage their well-being.
   
   We are constantly improving patient’s engagement to boost their treatment and ultimately reduce health care costs for the benefit of everyone.

  
VP Engineering 
 : Mediteo GmbH
  __2015 – 2016__
  
 : I built a distributed team of passion-driven professionals. 
 In over 150 interviews I hired the best international talents to join our team. I’ve established an interview process to hire based on communication skills and core­values over technical experience.
   
Lead Software Developer
 : Bonusbox GmbH
  __2012 - 2015__
  
 : We developed our platform as micro­services in Ruby and Erlang which communicated over RabbitMQ (as message bus). We hosted our software on AWS and implemented infrastructure­ as­ code using Ansible as provisioning tool to fully automate the server­ setup, scaling and maintenance. We followed code­ reviews to communicate best­ practices, pair programming, test driven development, SOLID design patterns and Even Driven Architecture.

Contractor - Technical Project Leader
 : Consileon Polska
  __2007 - 2012__
 : We built a number of products for our customers (Banking, E-Commerce, Startups). With using best tools for the job (Java, Erlang, Ruby on Rails, Django). I Led team of Engineers responsible for design and implementation. I organize internal Workshops (Software Engineering, Scrum/Agile). I represented company on Conferences as speaker.

Software Architect
 : T3 S.C
  __2007 - 2007__
 : We built a business intelligence system for one biggest Insurance
   company in Poland (Java EE).  
   We built our own product - invoicing system.

Senior Software Developer
 : Accenture Sp. z o.o.
  __2006 - 2007__
 : We built a new CRM for one of biggest Polish Telecoms, we migrated 
 platform to Java Technology. I was responsible for building full integrations between CRM and Lotus Notes - integrations of Leads notification, scheduling meetings / calls directly in Lotus Notes calendar.

Software Developer
 : Prolife Software Developer
  __2005 - 2006__
 : We built a Decision Support System for Emergency and call centers,
 fully integrated for automation and communication hardware.
 We built dedicated time control system for local court.

Software Developer
 : Systemhaus Scheuschner Gmbh
  __2005 - 2006__
 : I built a mobile application for tracking travels costs of Ambulances for Insurance Customers.
 I built a device drivers / servers (multithreaded) for Decision Support System and Telecommunication


-------

### Skills {#interests}

1. Ruby / Ruby on Rails - **Expert**
2. RSpec / Capybara / Cucumber - **Advanced**
2. Erlang / Elixir / Phoenix - **Expert**
3. Python / Django - **Advanced** 
4. JavaScript / Node.js - **Advanced**
5. Java / Spring / JavaEE - **Expert**
6. Clojure / ClojureScript - **Advanced**
7. React.js - **Intermediate**
8. JQuery - **Advanced**
8. Ember.js - **Advanced**
8. Knockout.js - **Advanced**
9. Android - **Advanced**
10. Postgres SQL, MySQL - **Advanced**
11. Riak, CouchDB, ElasticSearch, Solr - **Advanced**
12. Amazon Web Services - **Expert**
13. Lambda Architecture - **Expert**
14. Clean, CQRS, Event Sourcing - **Advanced**
15. Domain Driven Design - **Intermediate**
16. Test Driven Development - **Expert**
17. Scrum, Kanban - **Advanced**
18. Apacha Cordova / Phonegap - **Advanced**
19. REST, WebServices, SOAP - **Expert**
20. C# .NET - **Advanced**
21. GIT, Subversion - **Advanced**

-------

### Interests {#interests}

1. Digital Health
2. Machine Learning
2. Compiler Construction
3. Functional Programming
4. Distributed Software
5. Home Automation
6. Hiking / Swimming / Biking
9. Wood working

------

### Teaching {#teaching}

#### Workshops
: **Scrum For Software Developers**, I-Tool Software
 __2009-2012__

: **Programming in Ruby**, I-Tool Software
 __2007-2012__

: **BDD Cucumber/RSpec in Ruby on Rails**, I-Tool Software
 __2007-2012__

: **Web development in Ruby on Rails**, I-Tool Software
 __2007-2012__

: **Programming in Java**, I-Tool Software
 __2007-2012__

: **Web development in JBoss SEAM**, I-Tool Software
 __2007-2012__

: **Maven - Basics**, I-Tool Software
 __2007-2012__

: **Maven - Writing Extensions**, I-Tool Software
 __2007-2012__

: **Git - Version Controll System**, I-Tool Software
 __2007-2012__



------
### Publications {#publications}
#### Magazines

: Andrzej L. Śliwa, **Cucumber & Rspec - OutsideIn approach in Ruby on Rails**, Software Developer Journal. [link](http://www.gmmobile.pl/pobieranie/Cucumber_Rspec_SDJ_3-2011.pdf)
__2009__

#### Book Reviewer
: Francesco Cesarini, Steve Vinoski, **Designing for Scalability with Erlang/OTP**, Technical Review
__2016__


------

### Presentations {#presentations}
#### Conference Presentations 
: Andrzej L. Śliwa, **GIT - Distributed Version Control System**, Java4People Conference
__2009__

: Andrzej L. Śliwa, **Cucumber & Java**, Java4People Conference
__2011__

------ 

### Footer {#footer}

Andrzej Lucjan Śliwa - andrzej.sliwa@i-tool.eu

------
