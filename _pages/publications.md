---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %}

{% include base_path %}

```liquid
{% raw %}{% include publications %}{% endraw %}
```

<br/>

# Examples

## All publications
To include every single publication in your csv file, use:

```liquid
{% raw %}{% include publications %}{% endraw %}
```

<details>
<summary><i>Example output</i></summary>
{% include publications %}
</details>
<br/>