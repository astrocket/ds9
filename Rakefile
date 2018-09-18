# -*- ruby -*-

require 'rubygems'
require 'hoe'

Hoe.plugins.delete :rubyforge
Hoe.plugin :minitest
Hoe.plugin :gemspec # `gem install hoe-gemspec`
Hoe.plugin :git     # `gem install hoe-git`

gem 'rake-compiler', '>= 0.4.1'
require "rake/extensiontask"

Hoe.spec 'ds9' do
  developer('Aaron Patterson', 'tenderlove@ruby-lang.org')
  self.readme_file   = 'README.md'
  self.history_file  = 'CHANGELOG.md'
  self.extra_rdoc_files  = FileList['*.md']
  extra_dev_deps << ['rake-compiler', '>= 0.4.1']

  self.spec_extras = {
    :required_ruby_version => '>= 2.2.2'
  }

  self.spec_extras[:extensions] = ["ext/ds9/extconf.rb"]
  Rake::ExtensionTask.new "ds9", spec do |ext|
    ext.lib_dir = File.join(*['lib', ENV['FAT_DIR']].compact)
  end
end

# vim: syntax=ruby
