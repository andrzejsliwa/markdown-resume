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
 __2016 - present__
 
 : I redefined the technical strategy of Mediteo by redesigning and choosing a more suitables architecture for the server infrastructure, the backend and all mobile clients. I led the engineering, product, design and QA teams.
   
   I built a distributed team of passionate professionals and successfully applied agile methodologies. 
   
   I encouraged the team to build quality software by following test-driven-development, pair-programming, domain-driven-design, CQRS and event-sourcing.
   
   I supported the CEO evolving the company’s mission, vision and goals to serve our customers as the best healthcare product provider to actively help customers managing their well-being.
   
   We are constantly improving the engagement of patients to boost their treatment and ultimately reduce health care costs for the benefit of everyone.

  
VP Engineering 
 : Mediteo GmbH
  __2015 - 2016__
  
 : I built a distributed team of passionate professionals. 
 In over 150 interviews I hired the best international talents to join our team. I’ve established an interview process to hire based on communication skills and core-values over technical experience.
   
Lead Software Developer
 : Bonusbox GmbH
  __2012 - 2015__
  
 : We developed our platform as micro-services in Ruby and Erlang which communicated over RabbitMQ (as a message-bus). We hosted our software on AWS and implemented infrastructure-as-code using Ansible as our provisioning tool to fully automate the server-setup, scaling and maintenance. We established code-reviews to communicate best-practices, pair programming, test driven development, SOLID design patterns and event-driven architecture.

Contractor - Technical Project Leader
 : Consileon Polska
  __2007 - 2012__
 : We built a number of products for our customers (Banking, E-Commerce, Startups) utilizing the best tool for the job (Java, Erlang, Ruby on Rails, Django). I led a team of engineers and I was responsible for design and implementation. I organized internal workshops (Software Engineering, Scrum/Agile). I represented the company on conferences as a speaker.

Software Architect
 : T3 S.C
  __2007 - 2007__
 : We built a business intelligence system for one of the biggest insurance companies in Poland (Java EE).  
   We built our own product, an invoicing system.

Senior Software Developer
 : Accenture Sp. z o.o.
  __2006 - 2007__
 : We built a new CRM for one of biggest Polish telecoms, we migrated the platform to Java. I was responsible for building full integrations between CRM and Lotus Notes - integrations for leads notifications, scheduling meetings and calls directly in the Lotus Notes calendar.

Software Developer
 : Prolife Software Sp. z o.o.
  __2005 - 2006__
 : We built a decision support system for emergency and call centers,
 fully integrated with automation and communication hardware.
 We built dedicated time control system for the local court.

Software Developer
 : Systemhaus Scheuschner Gmbh
  __2005 - 2006__
 : I built a mobile application for tracking travel-costs of ambulances for insurance customers.
 I built device drivers and multithreaded servers for decision support system and telecommunication.


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
