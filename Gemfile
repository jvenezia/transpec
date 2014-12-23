source 'https://rubygems.org'

gemspec

group :development, :test do
  version = ENV['RSPEC_VERSION'] || '2.14'

  case version
  when 'head'
    %w(rspec rspec-core rspec-expectations rspec-mocks rspec-support).each do |lib|
      gem lib, git: "git://github.com/rspec/#{lib}.git"
    end
  when /^\d+\.\d+$/
    gem 'rspec', "~> #{version}.0"
  else
    fail 'RSPEC_VERSION must be specified as "major.minor" like "2.14", or "head".'
  end

  gem 'rake',      '~> 10.1'
  gem 'simplecov', '~> 0.7'
  gem 'rubocop',   '~> 0.24'
end

group :development do
  gem 'fuubar',        '>= 1.3', '< 3.0'
  gem 'guard-rspec',   '>= 4.2.3', '< 5.0'
  gem 'guard-rubocop', '~> 1.0'
  gem 'guard-shell',   '~> 0.5'
  gem 'ruby_gntp',     '~> 0.3'
end

group :test do
  gem 'coveralls',      '~> 0.6'
end
