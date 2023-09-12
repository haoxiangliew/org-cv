- [[org-cv](https://github.com/haoxiangliew/org-cv)](#org301a60e)
  - [Changes](#org4ba66d6)
  - [Installation](#orgccf950a)
  - [Usage](#org9530cf9)



<a id="org301a60e"></a>

# [org-cv](https://github.com/haoxiangliew/org-cv)

-   Follows upstream at <https://gitlab.com/Titan-C/org-cv>


<a id="org4ba66d6"></a>

## Changes

-   Added entries for org-cv in `org-export-dispatch`
-   Removed everything other than `ox-moderncv`


<a id="orgccf950a"></a>

## Installation

```emacs-lisp
(use-package ox-moderncv
  :elpaca (ox-moderncv :repo "https://github.com/haoxiangliew/org-cv")
  :requires ox-moderncv)
```


<a id="org9530cf9"></a>

## Usage

| Field    | Description                           |
|-------- |------------------------------------- |
| TITLE    | Desired Field                         |
| AUTHOR   | Name                                  |
| EMAIL    | Contact Email                         |
| TITLE    | Address, can span over multiple lines |
| HOMEPAGE | URL to website                        |
| MOBILE   | Mobile phone #                        |
| GITHUB   | GitHub User                           |
| GITLAB   | GitLab User                           |
| LINKEDIN | LinkedIn Username                     |
| PHOTO    | Path to photo file                    |

```org
# CV theme - options include: 'casual' (default), 'classic', 'oldstyle' and 'banking'
#+CVSTYLE: banking
# CV color - options include: 'blue' (default), 'orange', 'green', 'red', 'purple', 'grey' and 'black'
#+CVCOLOR: green

#+TITLE: My dream job
#+AUTHOR: John Doe
#+email: john@doe.lost

#+ADDRESS: My Awesome crib
#+ADDRESS: Fantastic city -- Planet Earth
#+MOBILE: (+9) 87654321
#+HOMEPAGE: example.com
#+GITHUB: Titan-C
#+GITLAB: Titan-C
#+LINKEDIN: oscar-najera
#+PHOTO: smile.png

* Employement
** One job
:PROPERTIES:
:CV_ENV:   cventry
:FROM:     <2014-09-01>
:TO:       <2017-12-07>
:LOCATION: a city, a country
:EMPLOYER: The employer
:END:

I write about awesome stuff I do.
** Other job
:PROPERTIES:
:CV_ENV:   cventry
:FROM:     <2013-09-01>
:TO:       <2014-08-07>
:LOCATION: my city, your country
:EMPLOYER: The other employer
:END:

I write about awesome stuff I do.

* Other stuff I do
- I work a lot
- I sleep a lot
- I eat a lot
```

-   <https://github.com/haoxiangliew/org-cv/blob/master/moderncv-demo.pdf>

When exporting you can call the following to get the latex file, or use `C-c C-e` / `org-export-dispatch`

```emacs-lisp
(org-export-to-file 'moderncv "moderncv.tex")
(org-latex-compile "moderncv.tex")
```