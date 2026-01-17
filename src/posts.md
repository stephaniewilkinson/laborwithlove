---
layout: default
title: Blog
---

<div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
  <div class="text-center mb-12">
    <h1 class="text-4xl font-serif font-bold text-primary-900 mb-4">Blog</h1>
    <p class="text-xl text-primary-800">Resources, stories, and insights for your birth journey.</p>
  </div>

  <div class="space-y-8">
    <% site.collections.posts.resources.sort_by { |p| -p.data.date.to_i }.each do |post| %>
      <article class="card">
        <time datetime="<%= post.data.date.to_date %>" class="text-sm text-primary-600 font-medium uppercase tracking-wide">
          <%= post.data.date.strftime("%B %d, %Y") %>
        </time>
        <h2 class="text-2xl font-serif font-bold text-primary-900 mt-2 mb-3">
          <a href="<%= post.relative_url %>" class="no-underline hover:text-primary-600 transition-colors">
            <%= post.data.title %>
          </a>
        </h2>
        <% if post.data.description %>
          <p class="text-primary-800 mb-4"><%= post.data.description %></p>
        <% end %>
        <a href="<%= post.relative_url %>" class="text-primary-600 font-medium no-underline hover:text-primary-700">
          Read more &rarr;
        </a>
      </article>
    <% end %>
  </div>
</div>
