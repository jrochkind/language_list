require 'bundler'
require 'csv'
Bundler::GemHelper.install_tasks

desc "compile languages.csv from languages.yml"
task :create_csv do
  key_order = [:name, :iso_639_1, :iso_639_3, :iso_639_2b, :iso_639_2t, :common, :type, :scope]

  giant_list = YAML.load_file(File.expand_path(File.join(File.dirname(__FILE__), 'data', 'languages.yml')))
  
  CSV.open(File.expand_path(File.join(File.dirname(__FILE__), 'data', 'languages.csv')), "wb") do |csv|
    giant_list.each do |hash|          
      csv << hash.values_at(*key_order)
    end
  end
  
end
