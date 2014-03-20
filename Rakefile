require 'active_support/core_ext/string'

name = 'nonlocal_spin_valve'
build_name = name.titlecase
tex_src = 'tex'
build = 'build'

task :default => :build

desc 'Build LaTeX.'
task build: [:tex]

desc 'Compile LaTeX to PDF.'
task :tex do
  FileUtils.mkdir_p build
  path = File.join tex_src, "#{name}.tex"

  fail RuntimeError, "Error: #{path} not found." unless File.exists? path

  Dir.chdir tex_src do
    system 'latexmk', '-xelatex', '-f', "#{name}.tex"
    FileUtils.mv "#{name}.pdf", File.join('../', build, "#{build_name}.pdf")
  end
end

desc 'Clean out temporary LaTeX files.'
task :clean do
  Dir.chdir tex_src do
    system 'latexmk', '-c'
    %w(fls bbl bib).each do |ext|
      Dir.glob("*.#{ext}") { |f| File.unlink f }
    end
  end
end
