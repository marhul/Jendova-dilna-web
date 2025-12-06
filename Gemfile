source "https://rubygems.org"

# Zachováváme požadovanou verzi Jekyllu.
# (Pokud byste chtěli novější, stačí změnit na "~> 4.3" nebo "~> 4.2")
gem "jekyll", "~> 4.2.0" 

# Tyto gemy jsou nutné, protože v nové verzi Ruby 3.4.x 
# již nejsou automaticky dostupné pro starší závislosti Jekyllu a musíme je přidat explicitně.
gem "csv"
gem "logger"
gem "base64"
gem "bigdecimal"

# Doporučeno: Umožňuje rychlejší instalaci.
group :development do
  gem "jekyll-watch"
end

# Volitelné: Vždy je dobré specifikovat verzi Bundleru (pokud ji znáte),
# ale v prostředí Netlify to není nezbytně nutné, protože si ji BuildBot vybere sám.
# gem "bundler", "~> 2.7"
