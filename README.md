To add materials to this website please submit a PR with the relevant additions. Materials can be added into the ```.yml``` files in the ```_data/materials``` and ```_data/4DEvents``` folders. Please try to add your materials to the correct file:
+ ```materials/full_courses``` should contain full semester (or quarter) long courses with open-source materials
+ ```materials/workshops``` should contain shorter multi-day workshops with open-source materials
+ ```materials/books``` should contain published books
+ ```materials/other_highlights``` will be updated by the site maintainers **please do not add materials to this file**
+ ```4DEvents/seminars``` should contain TinyMLedu run seminars
+ ```4DEvents/talks``` should contain all other global talks on TinyML
+ ```4DEvents/others``` should contain all other materials (demos, walkthroughs, etc.)

An example of a ```.yml``` file follows below for a talk. You'll notice that these fiels are just structured tex, ```-``` indicates a list, ```text:``` is a named value, all values should be placed in ```""``` and **indentation matters** as it indicates the level in the ```yml``` object. Note that for our specific syntax, each entry is an item in the meta list and you can add as many authors, links, and thumbnails as you'd like as they are sub-lists. If you need to upload images, slides, handouts, etc. please place them in the ```assets``` folder under the correct type (```images/thubnails```,```slides/4D```,```other/4D```, etc.). The book ```.yml``` follows a slightly modified syntax but the exisitng entries should provide sufficient examples. Finally, if you submit a workshop make sure to tag if it is a "4D_Event" so it shows up on the 4D page if relevant.
```
- authors:
    - name: "Marcelo Rovai"
      url: "https://github.com/Mjrovai"
    - name: "Marco Zennaro"
      url: "http://users.ictp.it/~mzennaro/"
  title: "IoT and TinyML Workshop"
  subtitle: "At the University of Namibia (UNAM)"
  date: "February 2, 2022"
  audience: "Everyone"
  language_instruction: "English"
  language_materials: "English"
  links:
    - url: "/assets/slides/4D/TSIoT_2022.pdf"
      title: "Slides"
  thumbnails:
    - image: "/assets/images/thumbnails/unifei.png"
      alt: "Universidade Federal de Itajubá (UNIFEI)"
      url: "https://unifei.edu.br/"
    - image: "/assets/images/thumbnails/ictp.svg"
      alt: "The Abdus Salam International Centre for Theoretical Physics (ICTP)"
      url: "https://www.ictp.it/"
```


## Testing your updates

If you know what you are doing just run this command

```
bundle exec jekyll serve
```

If you have agithub login try using gitpod by adding gitpod.io/# to the tinyMLx URL


gitpod.io/#https://github.com/tinyMLx/tinyMLx.github.io

Then run 


```
bundle exec jekyll serve
```

and open up a browser window. Then make your edits live and copy the files you changed to your fork of the tinyMLx repo and send a pull request PR.



If you have any questions / comments / concerns please reach out to the site maintainers at edu@tinyml.org.

== License ==

Copyright (c) 2022 TinyMLedu. All rights reserved.

[![License: CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/80x15.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
