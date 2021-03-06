require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "gridfs-rackdav"
    gem.summary = "GridFS resource adapter for RackDAV"
    gem.description = "gridfs-rackdav enables you to use GridFS as backend for WebDAV collections with RackDAV application"
    gem.email = "konjevic@gmail.com"
    gem.homepage = "http://github.com/retro/gridfs-rackdav"
    gem.authors = ["Mihael Konjević"]
    gem.add_development_dependency "rspec", ">= 1.2.9"
    gem.add_dependency('georgi-rack_dav', '>= 0.1.1')
    gem.add_dependency('mongodb-mongo', '>= 0.1')
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :spec => :check_dependencies

task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "gridfs-rackdav #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
