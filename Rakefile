require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "serialized_attributes"
  gem.homepage = "http://github.com/emmapersky/serialized_attributes"
  gem.license = "MIT"
  gem.summary = %Q{Simple serialization of row level attributes}
  gem.description = %Q{Serialize model attributes to a single database column instead}
  gem.email = "emma.persky@gmail.com"
  gem.authors = ["Emma Persky"]
  
  gem.add_runtime_dependency 'activerecord', '~> 3.0.0'
  gem.add_development_dependency 'sqlite3'
  gem.add_development_dependency 'jeweler'
  gem.add_development_dependency 'bundler'
  
  gem.files = [
    "Gemfile",
    "Gemfile.lock",
    "lib/serialized_attributes.rb",
    "lib/serialized_attributes/has_references_to.rb",
    "lib/serialized_attributes/serialized_attributes.rb",
    "LICENSE.txt",
    "Rakefile",
    "README.md",
    "test/simple_test.rb",
    "VERSION",
  ]
  
  gem.require_paths = ["lib"]
  # Include your dependencies below. Runtime dependencies are required when using your gem,
  # and development dependencies are only needed for development (ie running rake tasks, tests, etc)
  #  gem.add_runtime_dependency 'jabber4r', '> 0.1'
  #  gem.add_development_dependency 'rspec', '> 1.2.3'
end
Jeweler::RubygemsDotOrgTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/*.rb'
  test.verbose = true
end

# require 'rcov/rcovtask'
# Rcov::RcovTask.new do |test|
#   test.libs << 'test'
#   test.pattern = 'test/**/*.rb'
#   test.verbose = true
# end

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "foo #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
