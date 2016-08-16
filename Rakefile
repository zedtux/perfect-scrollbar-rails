require 'bundler/gem_tasks'
require 'fileutils'

desc 'Update the perfect-scrollbar Javascript and CSS files'
task :update do
  def working_dir
    'tmp'
  end

  def ensure_working_dir_exists!
    FileUtils.mkdir_p(working_dir)
  end

  def zip_path
    File.join(working_dir, 'perfect-scrollbar.zip')
  end

  def download(version)
    base_url = 'https://github.com/noraesae/perfect-scrollbar/releases/download'
    final_url = "#{base_url}/#{version}/perfect-scrollbar.zip"
    puts "Downlading perfect-scrollbar #{version} ..."
    `curl -Lfo #{zip_path} #{final_url}`
  end

  def extract
    puts 'Extracting perfect-scrollbar archive ...'
    `unzip -d #{working_dir} #{zip_path}`
  end

  def move_files
    puts 'Installating assets files ...'
    `mv #{working_dir}/js/perfect-scrollbar.jquery.js \
        vendor/assets/javascripts/perfect-scrollbar.js`
    `mv #{working_dir}/css/perfect-scrollbar.css vendor/assets/stylesheets`
  end

  def clean
    `rm -rf #{working_dir}`
  end

  FileUtils.mkdir_p('vendor/assets/javascripts')
  FileUtils.mkdir_p('vendor/assets/stylesheets')
  ensure_working_dir_exists!
  download(PerfectScrollbar::Rails::VERSION)
  extract
  move_files
  clean

  puts "\e[32mDone!\e[0m"
end
