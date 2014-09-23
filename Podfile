platform :ios, '7.0'
pod 'UMengAnalytics',    '~> 3.1.2'
pod 'ParseKit',          '~> 0.7'
pod 'UIImage+Additions', '~> 1.1.0'
pod 'UIImageEffects',    '~> 0.0.1'
pod 'MTMigration',       '~> 0.0.3'
pod 'iOS-blur',          '~> 0.0.5'
pod 'LMAlertView',       '~> 1.1.0'
pod 'RBStoryboardLink',  '~> 0.1.0'
pod 'OCMock',            '~> 3.0.2'
pod 'Reveal-iOS-SDK'    

inhibit_all_warnings!

post_install do |installer|
  default_library = installer.libraries.detect { |i| i.target_definition.name == 'Pods' }
  config_file_path = default_library.library.xcconfig_path

  File.open("config.tmp", "w") do |io|
    io << File.read(config_file_path).gsub(/-licucore/, '')
  end

  FileUtils.mv("config.tmp", config_file_path)
end
