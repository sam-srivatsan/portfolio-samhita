---
layout: doc
---

<script setup>
  import {data as blogs} from './assignments/assignment.data';
  import { withBase } from 'vitepress';
</script>

# Blogs

<ul v-if="assignments.length > 0">
  <li v-for="assignment of assignments">
    <a :href="withBase(assignment.url)">{{ blog.frontmatter.title }}</a>
  </li>
</ul>
<p v-else>
  Nothing here yet!
</p>
