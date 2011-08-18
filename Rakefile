# coding: utf-8

require 'rubygems'
require 'bundler/setup'
require 'redcarpet'
require 'pdfkit'

desc 'convert markdown to pdf.'
task :md2pdf, 'file_path'
task :md2pdf do |t, args|
  file_path = args.file_path

  md = File.open(file_path, 'r')
  options = [:hard_wrap, :filter_html, :autolink, :no_intraemphasis, :fenced_code, :gh_blockcode, :tables]
  html = Redcarpet.new(md.read, *options).to_html
  kit = PDFKit.new(html)
  kit.stylesheets << 'markdown.css'
  kit.to_file("#{file_path}.pdf")
end
   
