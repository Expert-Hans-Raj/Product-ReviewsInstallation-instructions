# Product-ReviewsInstallation-instructions


# Add reviews to your product pages
# This code snippet displays reviews on your product pages and adds SEO-friendly review scores to your Google search results.

# Copy the following code snippet to your clipboard:

<div id="shopify-product-reviews" data-id="{{product.id}}">{{ product.metafields.spr.reviews }}</div>

# Paste the snippet in your sections/product-template.liquid file where you want your reviews to appear. Usually this is just below the product.description tag, the code may look something like this:

<div class="product-single__description rte" itemprop="description">
  {{ product.description }}
</div>

<div id="shopify-product-reviews" data-id="{{product.id}}">{{ product.metafields.spr.reviews }}</div>

{% if section.settings.show_share_buttons %}
  {% include 'social-sharing', share_title: product.title, share_permalink: product.url, share_image: product %}
{% endif %}

# Once added, save your theme.

# Optionally add the star ratings badge to your collection pages

# Copy the following code snippet to your clipboard:

<span class="shopify-product-reviews-badge" data-id="{{ product.id }}"></span>

# Paste the snippet in your snippets/product-grid-item.liquid file where you want your star ratings to appear. Usually this is just below the product title and price, the code may look something like this:

<div class="grid-view-item{% unless product.available %} product-price--sold-out grid-view-item--sold-out{% endunless %}">
  <a class="grid-view-item__link" href="{{ product.url | within: collection }}">
    <img class="grid-view-item__image" src="{{ product.featured_image.src | img_url: grid_image_width, scale: grid_image_scale }}" alt="{{ product.featured_image.alt }}">
    <div class="h4 grid-view-item__title">{{ product.title }}</div>
    {% if section.settings.show_vendor %}
      <div class="grid-view-item__vendor">{{ product.vendor }}</div>
    {% endif %}
    <div class="grid-view-item__meta">
      {% include 'product-price' %}
    </div>
    <span class="shopify-product-reviews-badge" data-id="{{ product.id }}"></span>
    </span>
  </a>
</div>
# Once added, save your theme.


# Verify the code snippet is working
# Once you've inserted the snippet into your theme, you can check to make sure everything is working correctly.

