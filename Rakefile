require "pry"

require "bundler/setup"
require "html/proofer"
require 'uri'
require "./ext/hw_system"

task :download do

  domain = URI(ENV["URL"]).hostname
  site_root = ENV["URL"]

  `wget \
     --recursive \
     --no-clobber \
     --page-requisites \
     --html-extension \
     --convert-links \
     --restrict-file-names=windows \
     --directory-prefix=./tmp/sites \
     --domains #{domain} \
     --no-parent \
         #{site_root}`
end

task :test do
  domain = URI(ENV["URL"]).hostname
  HTML::Proofer.new(
    "./tmp/sites/#{domain}",
    check_html: false,
    allow_hash_href: true,
    empty_alt_ignore: true,
    typhoeus: { verbose: true, timeout: 5 },
    parallel: { in_processes: HWSystem.processor_count }
  ).run
end

task default: [:download, :test]
