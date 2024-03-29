---
layout: post
title:  How to install Bootstrap and jQuery in Rails 7 app with importmap
date:   2022-10-01 07:22:05 -0700
categories: development
path: "development"
tags: ["Ruby on Rails"]
---


#### First, add to your Gemfile
```ruby
gem 'jquery-rails'
gem 'bootstrap'
gem 'sassc-rails'
```
And run ```bundle install```

### Rename ```app/assets/stylesheets/application.css``` to ```app/assets/stylesheets/application.scss```

#### Then, add to ```application.scss``` above
```scss
@import "bootstrap";
```

#### Add to ```config/importmap.rb```
```ruby
pin "jquery", to: "jquery.min.js", preload: true
pin "jquery_ujs", to: "jquery_ujs.js", preload: true
pin "popper", to: "popper.js", preload: true
pin "bootstrap", to: "bootstrap.min.js", preload: true
```

#### Add to ```app/javascript/application.js```
```js
import "jquery"
import "jquery_ujs"
import "popper"
import "bootstrap"
```

#### Add to ```assets/config/manifest.js```
```js
//= link jquery.min.js
//= link jquery_ujs.js
//= link popper.js
//= link bootstrap.min.js
```

#### This is all you need to have Bootstrap and jQuery fully working

#### I also created a video to show it. You can check it out on Youtube here:

<iframe width="560" height="315" src="https://www.youtube.com/embed/C1ySLawZJ8Q" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br />