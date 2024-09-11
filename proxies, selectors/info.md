selectors:

import re

broker=response.css("span.BrokerTitle_titleText__RvFV6::text").get().replace("Brokered by ", "")
price = re.sub(r'[$,]', '', response.css("div.Pricestyles__StyledPrice-rui__btk3ge-0::text").get())

beds=response.css('li[data-testid="property-meta-beds"] span[data-testid="meta-value"]::text').get()
baths = response.css('li[data-testid="property-meta-baths"] span[data-testid="meta-value"]::text').get()
sqft= re.sub(r'[,]', '', response.css('li[data-testid="property-meta-sqft"] span[data-testid="meta-value"]::text').get())
acre_lot = response.css('li[data-testid="property-meta-lot-size"] span[data-testid="meta-value"]::text').get()

address_line1=response.css('div.card-address.truncate-line div[data-testid="card-address-1"]::text').get()
address_line2=response.css('div.card-address.truncate-line div[data-testid="card-address-2"]::text').get()

address_concat=address_line1 + ", " +address_line2

label = response.css('span[data-testid="label-new"] span::text').get()


all_properties= response.css('div#placeholder_property_2487278420')

base_url="https://www.realtor.com"
page_url="/realestateandhomes-search/Colorado/sby-6/pg-2"

next_page = response.css('div.base__StyledAnchor-sc-85657d15-0.DdDWT.next-link::attr(href)').get()

https://www.realtor.com/realestateandhomes-search/Colorado/sby-6/pg-1