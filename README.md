# pb-rules-overview

A drop-in admin page to quickly see all your [PocketBase](https://pocketbase.io/docs/api-rules-and-filters/) API rules in one place, eg for a security audit or sanity check.



**Contents**

 - [Getting Started](#getting-started)
 - [Usage Notes](#usage-notes)
 - [Technical Details](#technical-details)
 - [Future Work](#possible-future-work)
 - [Contact](#contact)

# Getting Started

1. Copy the `rules-overview.html` file into the `pb_public/` folder on your PB server, or wherever you've specified with `--publicDir`.

3. If you aren't already, login to the normal `/_` admin dashboard of your server (eg `http://localhost:8090/_`). The rules overview page piggybacks this auth token.

4. Access the rules overview at the `/rules-overview.html` path of your server (eg `http://localhost:8090/rules-overview.html`). NB: PB doesn't automatically do pretty URLs so the `.html` extension is required.

# Usage Notes

Hardcoded to only get 1000 collections in a single request. If you have more than that then you can change the `perPage` parameter in the `init()` function. 

# Technical Details

Built against PocketBase v0.34.2, but theoretically will probably work for anything v0.23 and up.

Piggybacks the CSS and auth of the existing PB admin dashboard, otherwise no dependencies.

# Possible Future Work

 - Edit API rules in place.
 - Also show defined `pb_hooks/` custom routes indicating access related middlware, eg `$apis.requireSuperuserAuth()`, `$apis.requireAuth()`, `$apis.requireGuestOnly()`, etc.
 - Safe loop to get all collections by pagination instead of the hardcoded single request limit.

# Contact

Raise an issue/discussion in this repo.
