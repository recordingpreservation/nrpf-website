# NRPF Website Documentation

This document provides guidance for adding and managing content on the National Recording Preservation Foundation (NRPF) website.

## Table of Contents

- [Feature Content](#news--blog-posts)
  - [Add a Blog/Feature Post](#add-a-blog-post)
  - [Add a Press Release](#add-a-press-release)
  - [Add a Podcast Episode](#add-a-new-podcast-episode-complete-workflow)
- [People & Team](#people--team)
  - [Add a Team Member](#add-a-team-member)
  - [Add a Podcast Team Member](#add-a-podcast-team-member)
- [Grants](#grants)
  - [Add a Grant](#add-a-grant)
- [Programs](#programs)
  - [Add a Program](#add-a-program)
- [Pages](#pages)
  - [Add a Static Page](#add-a-static-page)
- [Redirects](#redirects)
  - [Create a Redirect](#create-a-redirect)

---

## News & Blog Posts

### Add a Blog Post

Blog posts are stored in the `_posts/` directory with a specific date format in the filename.

**Location:** `_posts/YYYY-MM-DD-post-title.md`

**Required Front Matter Fields:**

```yaml
---
title: "Post Title"
date: 2024-04-14
author: "Author Name"
categories:
  - blog
description: "Brief description for SEO and previews"
layout: post
---
```

**Optional Front Matter Fields:**

```yaml
image: "/images/blog/featured-image.jpg"
fullWidth: true              # Use full-width layout
categories:
  - podcast                  # Additional categories
  - events
  - community
```

**Example:**

```yaml
---
title: "Announcing New Grant Recipients"
date: 2024-12-01
author: "Jesse Johnston"
categories:
  - blog
  - grants
description: "NRPF awards $150,000 in preservation grants"
image: "/images/blog/grants-2024.jpg"
layout: post
---

We are excited to announce the recipients of our 2024 grant cycle...
```

Posts will automatically appear on the blog page in reverse chronological order.

---

### Add a Press Release

Press releases are stored in the `_news/` directory and use a specific layout for formal announcements and media distribution.

**Location:** `_news/YYYY-MM-DD-descriptive-title.md`

**Required Front Matter Fields:**

```yaml
---
title: "Press Release Title"
date: 2024-03-11
location: "Washington, D.C."
author: "Author Name"
categories:
  - news
  - press releases
type: press release
layout: "press-release"
release:
tags:
  - National Recording Preservation Foundation
  - relevant tag
  - press release
image: images/social/NRPF-mandala-title-white-blue.png
description: "Brief summary for SEO and social media sharing"
---
```

**Field Descriptions:**

- `title`: The headline of the press release
- `date`: Publication date in YYYY-MM-DD format
- `location`: Dateline location (typically "Washington, D.C.")
- `author`: Person responsible for the release
- `categories`: Must include `news` and `press releases`
- `type`: Must be set to `press release`
- `layout`: Must be set to `"press-release"`
- `release`: Leave blank (used by the layout)
- `tags`: Array of relevant keywords for categorization
- `image`: Social media sharing image (typically use the default NRPF image)
- `description`: 1-2 sentence summary for previews and SEO

**Example:**

```yaml
---
title: "Librarian of Congress Appoints New Directors to the National Recording Preservation Foundation"
date: 2024-03-11
location: "Washington, D.C."
author: "Jesse Johnston"
categories:
  - news
  - press releases
type: press release
layout: "press-release"
release:
tags:
  - National Recording Preservation Foundation
  - Board of Directors
  - Librarian of Congress
  - audio preservation
  - press release
image: images/social/NRPF-mandala-title-white-blue.png
description: "Dr. Carla Hayden has appointed seven new directors to the National Recording Preservation Foundation's Board of Directors."
---

Dr. Carla Hayden, the 14th Librarian of Congress, has appointed seven new directors to the National Recording Preservation Foundation's Board of Directors, effective immediately...
```

**Press Release Content Guidelines:**

1. **Opening Paragraph**: Include who, what, when, where, and why in the first paragraph
2. **Body**: Provide supporting details, quotes, and background information
3. **Boilerplate**: Include standard information about NRPF
4. **Contact Information**: End with website URL and contact email:
   ```markdown
   For more information, please visit the National Recording Preservation Foundation's website at <https://www.recordingpreservation.org/> or contact [info@recordingpreservation.org](mailto:info@recordingpreservation.org).
   ```

**Tips:**

- Use professional, formal tone throughout
- Include relevant quotes from leadership or stakeholders
- Add hyperlinks to referenced resources or pages
- Keep paragraphs focused and concise
- Use the standard NRPF social image unless there's a specific visual asset

Press releases will appear in the news section and can be distributed to media contacts.

---

### Add a New Podcast Episode (Complete Workflow)

When publishing a new podcast episode, you need to update two files to ensure the episode appears correctly across the site. Follow these steps in order:

#### Step 1: Create a Blog Post for the Episode

Create a feature blog post that provides detailed information about the episode.

**Location:** `_posts/YYYY-MM-DD-soundfiles-ep##-descriptive-title.md`

**Example:** `_posts/2025-10-22-soundfiles-ep04-citizen-dj.md`

**Required Front Matter:**

```yaml
---
title: "Citizen DJ Drops a New Spin on History"
date: 2025-10-22
author: "Jesse Johnston"
categories:
  - blog
  - podcast
  - sound files
  - community
  - audio preservation
  - [other relevant categories]
description: "Brief description for SEO and social sharing (can include HTML tags like <em>)"
image: "/images/podcast/soundfiles-ep04-cover.png"
episode_number: 4
episode_description: "1-2 sentence description (optional, can leave empty)"
episode_date: 2025-10
episode_title: "Citizen DJ: A New Spin on Historical Sound Preservation"
podcast_episode: true
---
```

**Critical Fields:**
- `categories`: **Must include `sound files`** for the episode to appear in Latest Episode
- `episode_number`: Episode number (must match the number in podcast-soundfiles.json)
- `episode_title`: Full episode title (used in Latest Episode display)
- `episode_date`: YYYY-MM format
- `podcast_episode`: Set to `true`
- `image`: Episode cover art or promo image
- `description`: Can include HTML tags for formatting

**Post Content Structure:**

```markdown
![NRPF Sound Files podcast cover image]({% raw %}{% link images/podcast/soundfiles-ep04-promo-insta2.png %}{% endraw %}){:style="float: left; max-width: 40%; padding: 0 15px 0 0px; margin-top: 0;"}

Opening paragraph introducing the episode and its main topic...

Additional paragraph(s) with more details about the episode content, guests, and topics discussed.

Links to relevant resources mentioned in the episode.

# Listen Now

{% raw %}{% assign episode_data = site.data.podcast-soundfiles.episodes | where: "number", page.episode_number | first %}
{% if episode_data.embed-code %}
{{ episode_data.embed-code }}
{% endif %}{% endraw %}

{% raw %}{% include podcast-subscribe-buttons.html %}{% endraw %}

### Episode Credits

Sound Files is presented by the National Recording Preservation Foundation (NRPF)...

Jesse Johnston, creator of Sound Files and a Clinical Assistant Professor at the University of Michigan School of Information, hosts the podcast. Teresa Carey is the senior producer, editor, and creative lead for Morse Alpha Studios, which produced this podcast. Writing is by Jacob Pinter, field production by Steve Lack, and sound engineering by Ben Carey. Original music by Evan Haywood.

## About the Podcast

{% raw %}{% include podcast-press-kit-button.html %}
{% endraw %}
```

**Important Notes:**
- The episode embed code is automatically pulled from `podcast-soundfiles.json` based on the `episode_number`
- No need to create separate include files for episode players
- The floated image should be episode-specific promo art if available

---

#### Step 2: Add Episode to podcast-soundfiles.json

Add the new episode data to the JSON file. Episodes should be added at the **top** of the episodes array.

**Location:** `_data/podcast-soundfiles.json`

**Add to the top of the `episodes` array:**

```json
{
  "number": 4,
  "title": "Citizen DJ: A New Spin on Historical Sound Preservation",
  "date": "2025-10-22",
  "description": "Explore the amazing world of Citizen DJ, a platform that lets you remix historical sounds in ways you never imagined. Join us, whether you're a history buff or just love fresh music, in this new episode of <em>Sound Files</em>!",
  "link": "https://podcast.recordingpreservation.org/episodes/citizen-dj-a-new-spin-on-historical-sound-preservation",
  "embed-code": "<iframe height=\"200px\" width=\"100%\" frameborder=\"no\" scrolling=\"no\" seamless src=\"https://player.simplecast.com/31fe0359-32a4-4baa-bdde-749419871fb3?dark=false\"></iframe>",
  "published": true,
  "featured": true
}
```

**Field Details:**
- `number`: Episode number (integer, must match `episode_number` in the blog post)
- `title`: Full episode title
- `guest`: Guest name (optional, omit field if no guest)
- `date`: Publication date in YYYY-MM-DD format
- `description`: Short description for episode listings (can include HTML tags like `<em>`)
- `link`: URL to the episode on your podcast hosting platform
- `embed-code`: HTML embed code from Simplecast with escaped quotes (`\"`)
- `published`: Set to `true` to make the episode visible
- `featured`: Set to `true` for featured episodes, `false` otherwise
- `is_trailer`: Only include and set to `true` for trailer episodes (omit for regular episodes)

**Important:** Make sure to escape quotes in the embed-code by using `\"` instead of `"`.

---

#### Step 3: Verify the Episode Displays Correctly

After completing the above steps, the episode should automatically appear in:

1. **Latest Episode Highlight** (`_includes/podcast-latest-episode.html`)
   - Displays the most recent post with `sound files` category
   - Shows episode title, guest, description, and embedded player
   - Links to the full blog post

2. **Most Recent Episodes List** (`_includes/podcast-episodes-recent.html`)
   - Displays the 3 most recent episodes from `podcast-soundfiles.json`
   - Shows episode player and links to blog post if available

3. **All Episodes Page** (`/programs/podcast/episodes/`)
   - Full archive of all published episodes

**Checklist:**
- [ ] Created blog post in `_posts/` with all required front matter fields
- [ ] Included `sound files` in categories
- [ ] Added episode to `_data/podcast-soundfiles.json` at the top of the array
- [ ] Verified `episode_number` matches in both JSON and blog post
- [ ] Ensured embed-code quotes are properly escaped in JSON (`\"`)
- [ ] Tested that episode appears in Latest Episode section
- [ ] Confirmed episode shows in Recent Episodes list
- [ ] Checked that blog post link works from episode players

**Common Issues:**
- **Episode doesn't show as Latest:** Ensure blog post has `sound files` in categories and the date is the most recent
- **Embed player not showing:** Check that iframe src URL is correct and quotes are properly escaped in JSON (`\"` not `"`)
- **Episode not linking to blog post:** Verify `episode_number` matches exactly between JSON and post front matter
- **Player appears twice:** Make sure you're using the automatic embed code method (not including a separate episode file)

---

## People & Team

### Add a Team Member

Team members are stored in the `_team/` directory. Each person gets their own markdown file.

**Location:** `_team/firstname-lastname.md`

**Required Front Matter Fields:**

```yaml
---
title: "Full Name"
date: 2024-01-01           # Date added
image: "images/team/firstname-lastname-200.jpg"
jobtitle: "Board Title"    # e.g., "Chair", "Secretary", "Treasurer"
sort_name: lastname        # Used for alphabetical sorting
---
```

**Optional Front Matter Fields:**

```yaml
linkedinurl: "https://www.linkedin.com/in/username"
personal_url: "https://example.com"
short_bio: "Brief affiliation or description"
promoted: true             # Set to true for Board of Directors
weight: 1                  # Lower numbers appear first (for promoted members)
role: board                # Options: "board", "ex-officio", "advisor", "emeritus_director"
staff: true                # Set to true for staff members
staff_role: "Job Title"    # e.g., "Executive Director", "Program Manager"
current_term_start: 2024   # For board members with terms
current_term_end: 2028
```

**Example:**

```yaml
---
title: "Jane Smith"
date: 2024-01-15
image: "images/team/jane-smith-200.jpg"
jobtitle: "Chair"
linkedinurl: "https://www.linkedin.com/in/janesmith"
short_bio: "Example University"
promoted: true
weight: 1
role: board
sort_name: smith
current_term_start: 2024
current_term_end: 2028
---

Jane Smith is the Chair of the NRPF Board of Directors...
```

**Team Member Display Locations:**

- **Board of Directors**: `promoted: true` + `role: board`
- **Ex Officio Members**: `role: ex-officio`
- **Advisory Board**: `role: advisor`
- **Staff Members**: `staff: true`
- **Former Directors**: `role: emeritus_director`
- **SoundFiles podcast**: `soundfiles_team: true` (Note: requires additional metadata fields as noted below)

---

### Add a Podcast Team Member

To add someone to the podcast team (host, producer, editor, etc.), add these fields to their team file:

**Required Fields:**

```yaml
soundfiles_team: true
podcast_role: "Host"       # e.g., "Host", "Producer", "Editor", "Sound Engineer"
podcast_bio: "Bio text specifically for the podcast page..."
podcast_team_order: 1      # Lower numbers appear first
```

**Example:**

```yaml
---
title: "Jesse A. Johnston"
soundfiles_team: true
podcast_role: "Host"
podcast_bio: "Jesse A. Johnston, M.S.I., Ph.D., serves as Executive Director and Secretary of NRPF..."
podcast_team_order: 1
linkedinurl: "https://www.linkedin.com/in/jesseajohnston"
personal_url: "https://www.jesseajohnston.net/"
---
```

The podcast team cards will display on `/programs/podcast/` with the member's photo, role, bio, and links.

---

## Grants

### Add a Grant

Grants are stored in the `_grants/` directory, typically organized by year and recipient.

**Location:** `_grants/YYYY-recipient-name.md`

**Required Front Matter Fields:**

```yaml
---
title: "Grant Project Title"
collection: grants
type: grant
amount: "$25,000.00"
year: 2024
recipient: Organization Name
location: "City, State"
---
```

**Optional Front Matter Fields:**

```yaml
url: "https://organization.org"          # Link to organization
project_url: "https://project-site.org"   # Link to project
image: "/images/grants/project-image.jpg"
```

**Example:**

```yaml
---
title: "Preserving Historic Radio Broadcasts"
collection: grants
type: grant
amount: "$30,000.00"
year: 2024
recipient: "State Historical Society"
location: "Madison, WI"
url: "https://example.org"
---

Funding to support the digitization of master audio recordings...
```

Grants will automatically appear in the grants listing page and can be filtered by year.

---

## Programs

### Add a Program

Programs are stored in the `_programs/` directory.

**Location:** `_programs/program-name.md`

**Required Front Matter Fields:**

```yaml
---
title: "Program Name"
permalink: "/programs/program-name/"
date: 2024-01-01
weight: 1                  # Order in programs listing (lower = higher)
teaser: "Brief description for listings"
layout: page               # or "podcast" for podcast page
description: "Full SEO description"
---
```

**Optional Front Matter Fields:**

```yaml
image: "/images/program-image.jpg"
campaign_donate_link: 'https://donate-link-here'
elevator_pitch: "One-line pitch for the program"
```

**Example:**

```yaml
---
title: "NRPF Grants Program"
permalink: "/programs/grants/"
date: 2023-01-01
weight: 1
teaser: "Supporting audio preservation projects nationwide"
layout: page
description: "NRPF provides grants to support audio preservation projects..."
image: "/images/programs/grants-hero.jpg"
---

The NRPF Grants Program provides funding to...
```

---

## Pages

### Add a Static Page

Static pages are stored in the `_pages/` directory.

**Location:** `_pages/page-name.md`

**Required Front Matter Fields:**

```yaml
---
title: Page Title
layout: page
permalink: /page-url/
description: "Page description for SEO"
---
```

**Optional Front Matter Fields:**

```yaml
bodyClass: page-custom-class    # Add custom CSS class
image: "/images/page-hero.jpg"  # Featured image
---
```

**Example:**

```yaml
---
title: About the National Recording Preservation Foundation
layout: page
permalink: /about/
description: "Learn about NRPF's mission and history"
bodyClass: page-about
---

The National Recording Preservation Foundation (NRPF) is...
```

---

## Redirects

### Create a Redirect

Redirects are useful for maintaining old URLs when content moves. Redirect files are stored in the root directory.

**Location:** `redirect-old-page-name.md`

**Required Front Matter Fields:**

```yaml
---
layout: redirect
sitemap: false
permalink: /old-url/
redirect_to: /new-url/
---
```

**Example:**

```yaml
---
layout: redirect
sitemap: false
permalink: /podcast/
redirect_to: /programs/podcast/
---
```

This creates a redirect from `/podcast/` to `/programs/podcast/`.

**Common Use Cases:**

- Moving pages to new locations
- Consolidating content
- Maintaining external links to old URLs
- Providing short URLs for marketing

---

## Additional Resources

### Image Guidelines

- **Team Photos**: 200x200px minimum, square crop, stored in `images/team/`
- **Featured Images**: 1200x630px for social media sharing
- **Program/Page Headers**: 1600x900px recommended

### Markdown Tips

- Use `{% raw %}{% link file.md %}{% endraw %}` for internal links to ensure they update correctly
- Use `{% raw %}{{ site.baseurl }}{% endraw %}` or `relative_url` filter for asset paths
- Front matter values can include HTML with `<em>` tags for italics

### Testing Changes Locally

1. Run `bundle exec jekyll serve` to start local server
2. Visit `http://localhost:4000` in your browser
3. Check that new content appears correctly
4. Verify all links work

---

## Getting Help

For questions or issues:
- Check existing files in each directory for examples
- Review Jekyll documentation at https://jekyllrb.com/docs/
- Contact the web administrator

**Last Updated:** 2025-10-22
