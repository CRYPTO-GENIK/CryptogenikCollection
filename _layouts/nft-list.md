---
# Mr. Green Jekyll Theme - v1.1.0 (https://github.com/MrGreensWorkshop/MrGreen-JekyllTheme)
# Copyright (c) 2022 Mr. Green's Workshop https://www.MrGreensWorkshop.com
# Licensed under MIT

layout: default
---
{% if site.data.conf.posts.post_query == true and site.data.conf.posts.post_query_tabs == true -%}
  {% include post-list/upside-down-tabs.html -%}
{% endif -%}

<div class="post-list-header"></div>

 <div class="nft-card-container">
<!----------- CONTAINER ------------->
  
  
  
  
  <div class="nft-card">
    <div class="nft-inner-card">
      <a href="https://neonrain.io/collections/0x4bd2a30435e6624CcDee4C60229250A84a2E4cD6/2832" class="nft-link">
        <div class="nft-resource-container">
          <div alt="NFT #2832" class="nft-resource" style="background-image: url('https://static-nft.pancakeswap.com/mainnet/0x4bd2a30435e6624CcDee4C60229250A84a2E4cD6/gamester-3375-1000.png');"></div>

          <div class="collection-title">
            <div font-size="12px" color="textSubtle" class="collection-subtitle">Syncronaut Ape</div>
          </div>
           <div class="nft-card-heart">
             <h4 font-weight="600" color="text" font-size="16px" class="nft-card-title">Syncronaut #2832</h4>
               <div class="heartbox">
                  <input class="toggle-heart" id="toggle-heart-1" type="checkbox" checked/>
                  <label class="toggle-heart-mark"  for="toggle-heart-1" aria-label="like">❤</label>
              </div>
          </div>
          <div class="nft-card-footer">
            <div class="nft-card-footer-text">
              <div font-size="12px" color="textSubtle" title="Asking price" class="nft-card-price">Asking price</div>
              <div class="nft-card-amounts-container">
                <div class="nft-card-amounts">
                  <div font-size="12px" color="textSubtle" class="nft-card-value-usd">($67.39)</div>
                  <div class="nft-card-value-crypto">
                    <svg viewBox="0 0 96 96" width="16px" color="text" xmlns="http://www.w3.org/2000/svg" class="nft-card-token-symbol">
                      <circle cx="48" cy="48" r="48" fill="#F0B90B"></circle>
                      <path d="M30.9008 25.9057L47.8088 16.0637L64.7169 25.9057L58.5007 29.5416L47.8088 23.3355L37.117 29.5416L30.9008 25.9057ZM64.7169 38.3179L58.5007 34.682L47.8088 40.8881L37.117 34.682L30.9008 38.3179V45.5897L41.5926 51.7958V64.2079L47.8088 67.8438L54.0251 64.2079V51.7958L64.7169 45.5897V38.3179ZM64.7169 58.0018V50.7301L58.5007 54.366V61.6377L64.7169 58.0018ZM69.1305 60.572L58.4386 66.7781V74.0499L75.3467 64.2079V44.524L69.1305 48.1599V60.572ZM62.9143 32.1118L69.1305 35.7477V43.0195L75.3467 39.3836V32.1118L69.1305 28.4759L62.9143 32.1118ZM41.5926 69.411V76.6828L47.8088 80.3187L54.0251 76.6828V69.411L47.8088 73.0469L41.5926 69.411ZM30.9008 58.0018L37.117 61.6377V54.366L30.9008 50.7301V58.0018ZM41.5926 32.1118L47.8088 35.7477L54.0251 32.1118L47.8088 28.4759L41.5926 32.1118ZM26.4872 35.7477L32.7034 32.1118L26.4872 28.4759L20.271 32.1118V39.3836L26.4872 43.0195V35.7477ZM26.4872 48.1599L20.271 44.524V64.2079L37.1791 74.0499V66.7781L26.4872 60.572V48.1599Z" fill="white"></path>
                    </svg>
                    <div font-weight="600" color="text" font-size="16px" class="nft-card-value-crypto">0.25</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </a>
    </div>
  </div>
  </div><!--end-->
<div class="post-list-container">
  {% for post in paginator.posts -%}
    {% include post-list/post-thumbnail-data.liquid post = post -%}
    {% include post-list/post-thumbnail-html.html
      url = post_url
      image = image
      max_width = max_width
      display = display
      title = page_title
      title_sub = title_sub
      date = post_date
      read_time = read_time
      comment_style = comment_style
    %}
  {% endfor -%}
</div>

{%-comment-%} Pagination {%-endcomment-%}
{% if paginator.total_pages > 1 -%}
  {%- assign blogpages = site.html_pages | where_exp: "item", "item.layout == 'post-list'" -%}
  {% include multi_lng/get-pages-by-lng.liquid pages = blogpages -%}
  {% if site.data.conf.posts.pager_navigation_post_list == 'prev_next_buttons' -%}
    {%- include post_common/pager-prev-next-buttons.html pages = lng_pages current_page_url = page.url side_aligned = site.data.conf.posts.pager_prev_next_buttons_side_aligned -%}
  {% elsif site.data.conf.posts.pager_navigation_post_list == 'page_numbers' %}
    {% include post_common/pager-page-numbers.html pages = lng_pages current_page_url = page.url -%}
  {% endif -%}
{% elsif site.data.conf.posts.pager_navigation_post_list == 'page_numbers' and site.data.conf.posts.pager_page_numbers_auto_generator -%}
  {% if site.data.conf.posts.post_query_mode_startup == 'paginator' or site.data.conf.posts.post_query_mode_query == 'paginator' %}
    {% include post_common/pager-page-numbers.html pages = nil current_page_url = page.url -%}
  {% endif -%}
{% endif -%}
