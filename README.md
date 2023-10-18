# IDC UI Theme boots
IDC's UI Theme based on the Bootstrap Barrio subtheme

## Tree structure
```shell
├── color
│   └── Color picker
├── config
│   ├── install
│   │   └── Drupal Configs to install with theme
│   └── schema
│       └── Drupal theme schema
├── css
│   └── CSS files
├── images
│   └── Images specific to theme like the logo
├── js
│   └── JS files
├── logo.svg <-- Logo
├── screenshot.png <-- Screenshot of homepage with this theme.
└── templates
    ├── Types
    │   └── Twig templates
    └── Twigs templates organized by types.

```

### Main menu comes from a Drupal migration. It is not part of the theme.

To see most recent screenshot go to
![](https://github.com/jhu-idc/idc_ui_theme_boots/blob/main/images/most_recent_screenshot.png)

<meta name="title" content="JHU Sheridan Library's Islandora Theme">
<meta name="description" content="IDC's UI Theme based on the Bootstrap Barrio subtheme">
<meta property="og:type" content="website">
<meta property="og:url" content="https://github.com/jhu-idc/idc_ui_theme_boots">
<meta property="og:title" content="Github repo for IDC's UI Theme">
<meta property="og:description" content="IDC's UI Theme based on the Bootstrap Barrio subtheme">
<meta property="og:image" content="https://github.com/jhu-idc/idc_ui_theme_boots/blob/main/images/most_recent_screenshot.png">
<meta property="twitter:card" content="summary_large_image">
<meta property="twitter:url" content="https://github.com/jhu-idc/idc_ui_theme_boots">
<meta property="twitter:title" content="Github repo for IDC's UI Theme">
<meta property="twitter:description" content="IDC's UI Theme based on the Bootstrap Barrio subtheme">
<meta property="twitter:image" content="https://github.com/jhu-idc/idc_ui_theme_boots/blob/main/images/most_recent_screenshot.png">

### How to edit content

#### Footer

#### Fallback collection thumbnail
 1. Go to admin/structure/views/view/top_level_collections/edit/page_1
 1. Click dropdown "For" > "This page (override)"
 1. Click in the "field" section > "(field_media_of) Media: Image"
 1. Within the "No results behavior" add the following standard HTML code:
```html
<!-- <img src="https://dummyimage.com/200x200/fff/aaa" style="max-width:200px;" /> -->

<img loading="lazy" src="/themes/contrib/idc_ui_theme_boots/images/jhu_library_fallback.jpg" width="220" height="110" alt="Johns Hopkins Peabody Library.jpg" typeof="foaf:Image" class="image-style-medium" style="max-width:200px;">
src="themes/contrib/idc_ui_theme_boots/images/fallback_collection_thumbnail.jpg"
```
 1. Apply (this display)

Possible Images for the fallback:
- https://www.library.jhu.edu/wp-content/uploads/sites/3/2017/06/peabody-banner-2.jpg
- https://www.library.jhu.edu/wp-content/uploads/sites/3/2017/06/peabody-banner-1.jpg
- https://www.library.jhu.edu/wp-content/uploads/sites/3/2017/06/qrr.jpg
- https://www.library.jhu.edu/wp-content/uploads/sites/3/2017/06/blc-1.jpg
- https://www.library.jhu.edu/wp-content/uploads/sites/3/2017/06/blc-2.jpg
- https://www.library.jhu.edu/wp-content/uploads/sites/3/2017/06/clevel-banner.jpg
- https://www.library.jhu.edu/wp-content/uploads/sites/3/2017/06/hut.jpg
- https://www.library.jhu.edu/wp-content/uploads/sites/3/2017/06/msel-atrium.jpg

#### Members of a Collection & Compound objects
Block is added by a context in /admin/structure/context/collection

#### Edit Collection View
Manage the displayed fields admin/structure/types/manage/collection_object/display


#### Turn off TWIG Debugging
Go to `sites/default/services.yml` and then modifying the twig.config section in services.yml to set `debug: false`.

#### Add a new theme twig suggestion
1. Go to `themes/contrib/idc_ui_theme_boots/idc_ui_theme_boots.theme`
1. Add a new suggestion in the `idc_ui_theme_boots_theme_suggestions_page_alter` function
1. Using existing examples `$variables['element']['#id']` that takes in the CSS ID of the element to know which template to suggest.
1. Clear cache

