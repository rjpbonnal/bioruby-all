# encoding: utf-8

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
  gem.name = "bio-all"
  gem.homepage = "http://github.com/helios/bioruby-all"
  gem.license = "MIT"
  gem.summary = %Q{All BioRuby plugins core, core-ext, dev, experimental, etc...}
  gem.description = %Q{All BioRuby plugins}
  gem.email = "ilpuccio.febo@gmail.com"
  gem.authors = ["Raoul J.P. Bonnal", "Pjotr Prins"]
  # dependencies defined in Gemfile
  gem.add_runtime_dependency 'bio-core'
  gem.add_runtime_dependency 'bio-core-ext'
  gem.add_runtime_dependency 'bio-cnls_screenscraper'
  gem.add_runtime_dependency 'bio-emboss_six_frame_nucleotide_sequences'
  gem.add_runtime_dependency 'bio-genomic-interval'
  gem.add_runtime_dependency 'bio-graphics'
  gem.add_runtime_dependency 'bio-hello'
  gem.add_runtime_dependency 'bio-isoelectric_point'
  gem.add_runtime_dependency 'bio-lazyblastxml'
  gem.add_runtime_dependency 'bio-nexml'  
  gem.add_runtime_dependency 'bio-octopus'
  gem.add_runtime_dependency 'bio-signalp'
  gem.add_runtime_dependency 'bio-tm_hmm'
end
Jeweler::RubygemsDotOrgTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

require 'rcov/rcovtask'
Rcov::RcovTask.new do |test|
  test.libs << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
  test.rcov_opts << '--exclude "gems/*"'
end

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "bio-all #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
