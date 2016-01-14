require 'html/proofer'
require './ext/hw_system'

task :download do
  domain = 'theironyard.com'
  site_root = 'https://www.theironyard.com/'

  `wget \
     --recursive \
     --no-clobber \
     --page-requisites \
     --html-extension \
     --convert-links \
     --restrict-file-names=windows \
     --domains #{domain} \
     --no-parent \
         #{site_root}`
end

task :test do
  HTML::Proofer.new(
    './www.theironyard.com',
    check_html: false,
    allow_hash_href: true,
    empty_alt_ignore: true,
    typhoeus: { verbose: true, timeout: 5 },
    parallel: { in_processes: HWSystem.processor_count }
  ).run
end

task default: [:download, :test]
