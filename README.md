# Choose a License Web Site

Like a Choose Your Own Adventure site, but only much less interesting.

# Intro

A lot of repositories on GitHub.com don't have a license. GitHub could slap on 
a license chooser, but if you don't know anything about licenses, how are you 
supposed to make an informed decision.

ChooseALicense.com is designed to help people make an informed decision about 
licenses. 

# Immediate Goals

* Politics Free - Let's just not get into it.
* Well designed, but that goes without saying.
* The homepage should have just enough to help 99% of folks make a decision.
* For the 1%, the site will contain a license chooser similar to 
the [creative commons license chooser](http://creativecommons.org/choose/)
* Not comprehensive. Seems like an odd goal, but there are a bajillion 
(I counted) licenses out there. We're going to have to filter that down to a 
small list of those that matter.

# Design

I think v1 of the site could be a completely static JavaScript site. No need 
for a back end until we actually need it.

# Community

We plan to build out the skeleton of the site privately first, but then open 
it up to accept contributions.

Phil will look into whether various open source foundations and lawyers would 
be interested in being involved. Probably makes good sense to have a lawyer 
review the content before we post it live.

# Run It On Your Machine

1. `git clone https://github.com/github/choosealicense.com`
2. `cd choosealicense.com`
3. `script/bootstrap`
4. `script/server`
5. Open [localhost:4000](http://localhost:4000) in your favorite browser

# Adding a license

Licenses sit in the `/licenses` folder as markdown (`.md`) files. Each license has YAML front matter describing the license's properties. The body of the markdown file should be the text of the license. The available metadata fields are:

* `title` - The name of the license
* `layout` - This should be `license`
* `permalink` - The url to the license relative to `/licenses/`
* `source` - URL to the license source text
* `note` - The note field in the sidebar (optional)
* `how` - How to use the license, also in the sidebar
* `required`, `permitted`, `forbidden` - bulleted list of rules applicable to the license (see below)

# Rules 

* Rules (the license's properties) are stored as a bulleted list within the licenses YAML front matter. A full list of rules can be found in the repository's `_config.yml` file. Each rule has a name e.g., `include-copyright`, a human-readable label, e.g., `Copyright inclusion`, and a description `Include the original copyright with the code`. To add a new rule, simply add it to config.yml and reference it in the appropriate license. 
