
      {{ with .Params.experience }}
      {{ if .enable }}


      <!-- DNS preconnect -->
<meta http-equiv="x-dns-prefetch-control" content="on">
<link rel="preconnect" href="//ajax.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous">
<link rel="preconnect" href="https://use.fontawesome.com" crossorigin>
<link rel="preconnect" href="//cdnjs.cloudflare.com">
<link rel="preconnect" href="//www.googletagmanager.com">
<link rel="preconnect" href="//www.google-analytics.com">
<link rel="dns-prefetch" href="https://fonts.gstatic.com">
<link rel="dns-prefetch" href="https://use.fontawesome.com">
<link rel="dns-prefetch" href="//ajax.googleapis.com">
<link rel="dns-prefetch" href="//cdnjs.cloudflare.com">
<link rel="dns-prefetch" href="//www.googletagmanager.com">
<link rel="dns-prefetch" href="//www.google-analytics.com">
<link rel="dns-prefetch" href="//fonts.googleapis.com">
<link rel="dns-prefetch" href="//connect.facebook.net">
<link rel="dns-prefetch" href="//platform.linkedin.com">
<link rel="dns-prefetch" href="//platform.twitter.com">

<!-- plugins + stylesheet -->
{{ $styles := slice }}
{{ range site.Params.plugins.css }}
{{ if findRE "^http" .link }}
<link crossorigin="anonymous" media="all" rel="stylesheet" href="{{ .link | relURL }}" {{.attributes | safeHTMLAttr}} >
{{ else }}
{{ $styles = $styles | append (resources.Get .link) }}
{{ end }}
{{ end }}
{{ $styles := $styles | append (resources.Get "scss/style.scss" | resources.ExecuteAsTemplate "style.scss" . | toCSS) }}
{{ $styles := $styles | resources.Concat "/css/style.css" | minify | fingerprint "sha512"}}
<style type="text/css">{{$styles.Content | safeCSS}}</style>


            <div class="form-group">
              <label for="name" class="form-label">{{ .Params.subject_title | markdownify }}<small> *</small></label>
              <input type="text" class="form-control" name="email[address]" id="subject" placeholder="{{ .Params.subject_placeholder | markdownify }}"
                required>
            </div>

            
      {{ with .image }}
      <div class="col-lg-6 col-sm-6 col-9 mx-auto mb-5 mb-lg-0">
        {{ partial "image.html" (dict "Src" . "Alt" "banner-img" "Class" "img-fluid" ) }}
      </div>
      {{ end }}


        
        {{ partial "image.html" (dict "Src" . "Alt" "banner-img" "Class" "img-fluid" ) }}

        <iframe width="560" height="315" src="https://www.youtube.com/embed/nMTkNY86zBg" title="Pantrypoints Circle" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


<!-- favicon -->
{{ partialCached "favicon" . }}


<!-- manifest -->
{{ partialCached "manifest" . }}


<!-- site verifications -->
{{ partialCached "site-verifications.html" . }}


<!-- opengraph and twitter card -->
{{ partial "basic-seo.html" . }}

<!-- custom script -->
{{ site.Params.custom_script | safeHTML}}


<!-- google analytics -->
{{ template "_internal/google_analytics.html" . }}


<!-- google tag manager -->
{{ partialCached "gtm.html" . }}


<!-- matomo analytics -->
{{ partialCached "matomo-analytics.html" . }}


<!--  Baidu analytics -->
{{ partialCached "baidu-analytics.html" . }}


<!-- Plausible Analytics -->
{{ partialCached "plausible-analytics.html" . }}


<!-- Counter Analytics -->
{{ partialCached "counter-analytics.html" . }}


<!-- Crisp Chat -->
{{ partialCached "crisp-chat.html" . }}





<h1 align=center>Geeky Hugo</h1> 
<p align=center>Get Geeked out by Geeky, a personal Hugo blog theme that is fully responsive and super-fast.</p>
<h2 align="center"><a target="_blank" href="https://demo.statichunt.com/geeky-hugo/" rel="nofollow">Demo</a> | <a  target="_blank" href="https://pagespeed.web.dev/report?url=https%3A%2F%2Fdemo.statichunt.com%2Fgeeky-hugo%2F&form_factor=desktop">Page Speed (85%)</a> </h2>


<p align=center>
  <a href="https://github.com/gohugoio/hugo/releases/tag/v0.87" alt="Contributors">
    <img src="https://img.shields.io/static/v1?label=min-HUGO-version&message=0.87&color=f00&logo=hugo" />
  </a>

  <a href="https://github.com/statichunt/geeky-hugo/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/statichunt/geeky-hugo" alt="license"></a>

  <img src="https://img.shields.io/github/languages/code-size/statichunt/geeky-hugo" alt="code size">

  <a href="https://github.com/statichunt/geeky-hugo/graphs/contributors">
    <img src="https://img.shields.io/github/contributors/statichunt/geeky-hugo" alt="contributors"></a>

  <a href="https://twitter.com/intent/follow?screen_name=heyStatichunt">
    <img src="https://img.shields.io/twitter/follow/heyStatichunt?style=social&logo=twitter"
      alt="follow on Twitter"></a>
</p>

---

<p align="center">
 
![geeky-hugo-startup-theme](https://user-images.githubusercontent.com/17677384/140605658-0c68cf6c-d15a-4f0d-8e66-1060ce636d20.png)
</p>

---
## Key Features
- Hugo module support
- Google analytics, AdSense support
- Image optimize  with hugo pipe
- CSS and JS bundle with hugo pipe
- Netlify settings predefine
- Forestry cms pre-configured
- Google font loads from webfont loader
- Caching enable
- Color and fonts variable in config file
- Contact form Support
- Search by fuse.js
- Mailchimp integrate
- GDPR consent enable
- Google page speed optimized
- Open graph meta tag
- Twitter card meta tag


## Local development

```bash
# clone the repository
git clone git@github.com:statichunt/geeky-hugo.git

# cd in the project directory
$ cd geeky-hugo/exampleSite/

# Start local dev server
$ hugo server --themesDir ../..
```
Or Check out [Full Documentation](https://docs.gethugothemes.com/geeky/?ref=github).

## Content Management System

[![import to
Forestry](https://assets.forestry.io/import-to-forestryK.svg)](https://app.forestry.io/quick-start?repo=statichunt/geeky-hugo&engine=hugo&version=0.87.0)

This project has been pre-configured to work with [Forestry](https://forestry.io) a git-based CMS, [import your
repository in Forestry](https://app.forestry.io/quick-start?repo=statichunt/geeky-hugo&engine=hugo&version=0.87.0) and
you will be able to edit and preview your site ✨.

Any changes you make in Forestry will be committed back to the repo and deployed if you use [Netlify](#netlify).
## Deployment and hosting

[![Deploy to
Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/statichunt/geeky-hugo)

Follow the steps.

## Prefer a video? (Hugo + Netlify + Forestry)
Build your website with **geeky hugo** theme by following these easy steps (No Coding Required!)
[Video Tutorial](https://youtu.be/ResipmZmpDU).

<!-- reporting issue -->
## Reporting Issues
We use GitHub Issues as the official bug tracker for the geeky Template. Please Search [existing
issues](https://github.com/statichunt/geeky-hugo/issues). Someone may have already reported the same problem.
If your problem or idea has not been addressed yet, feel free to [open a new
issue](https://github.com/statichunt/geeky-hugo/issues).

<!-- ## geeky hugo theme Powered Websites

View all the websites powered by geeky hugo theme [here](https://github.com/statichunt/geeky-hugo/wiki/All-Geeky-Hugo-Powered-Websites). Want to submit your own website powered by geeky hugo theme? You can submit it [here](https://github.com/statichunt/geeky-hugo/discussions/2). -->

<!-- licence -->
## License
Copyright &copy; Designed and developed by [Statichunt](https://statichunt.com)

**Code License:** Released under the [MIT](https://github.com/statichunt/geeky-hugo/blob/master/LICENSE) license.

**Image license:** The images are only for demonstration purposes. They have their licenses. We don't have permission to
share those images.

<!-- resources -->
## Special Thanks
- [Bootstrap](https://getbootstrap.com)
- [Jquery](https://jquery.com)
- [Font Awesome Icons](https://fontawesome.com)
- [Fuse Js](https://fusejs.io)
- [Google Fonts](https://fonts.google.com/)
- [All Contributors](https://github.com/statichunt/geeky-hugo/graphs/contributors)
