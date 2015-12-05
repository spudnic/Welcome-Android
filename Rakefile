# encoding: utf-8

def run_command(command)
  if File.exist?('Gemfile.lock')
    sh %(bundle exec #{command})
  else
    sh %( #{command})
  end
end

namespace :ci do
  desc 'run the unit tests'
  task :unit do
    run_command('echo "run unit tests"')
  end
  desc 'run the integration tests'
  task :integration do
    run_command('echo "run integration tests"')
  end
  desc 'build the app'
  task :build do
    run_command('./gradlew clean build')
  end
end

task default: ['ci:build', 'ci:unit', 'ci:integration']

