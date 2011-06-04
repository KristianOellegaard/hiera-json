require 'rubygems'
require 'rake/gempackagetask'
require 'rspec/core/rake_task'

spec = Gem::Specification.new do |s|
  s.name = "hiera-json"
  s.version = "0.0.1"
  s.author = "R.I.Pienaar"
  s.email = "rip@devco.net"
  s.homepage = "http://devco.net/"
  s.platform = Gem::Platform::RUBY
  s.summary = "JSON backend for the Hiera hierarcical data store"
  s.description = "Store Hiera data in JSON"
  s.files = FileList["{bin,lib}/**/*"].to_a
  s.require_path = "lib"
  s.test_files = FileList["{test}/**/*test.rb"].to_a
  s.has_rdoc = true
  s.extra_rdoc_files = ["README.md"]
  s.add_dependency('hiera')
  s.add_dependency('json')
end

Rake::GemPackageTask.new(spec) do |pkg|
  pkg.need_tar = true
end

desc "Run all specs"
RSpec::Core::RakeTask.new(:test) do |t|
    t.pattern = 'spec/**/*_spec.rb'
    t.rspec_opts = File.read("spec/spec.opts").chomp || ""
end
