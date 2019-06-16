# Flutter application templates

This repository is to used to maintain some templates that can form the basis of a Flutter application. These templates may be opinionated in how to structure applications. The intent is that these templates could help other developers get started sooner in the absence of being able specify templates to use to the `flutter create` command.

## Templates 
Templates can be found in the following folders

- `material_bottomnavigation_provider_mobx` - a template for a material design application with bottom navigation, provider and MobX

## Getting started with a template

When creating a brand new Flutter application, there are few steps that developers may do

- specify the organisation 
- specify the name of the app
- specify the languages used for the Android and iOS projects

Note that out of the box, Flutter will combine the organisation and name of the app to set that as the bundle identifier of your Android and iOS application. It is still possible to do all of the above with a template. The following steps are required
1. Clone this repository
2. Pick the folder/template you'd like to use and copy it to the location of your choice. Let's assume for this example that you have picked the `material_bottomnavigation_provider_mobx` folder and copied it to sit within `projects` folder
3. Go to the `projects` folder (i.e. where you've copied the template to). Rename the folder to match the name of your application e.g. `counter`. This is crucial as Flutter's tooling actually uses this as portion of the bundle identifier that represents your application's name
4. Open the `counter` application in your IDE of choice, search for all instances of `material_bottomnavigation_provider_mobx` and replace it with `counter` (the name of your application)
5. From the root folder of your `counter` application. Run the following command

```
flutter create --org <organisation> -a <android_language> -i <ios_language> .
```

where `organisation>` is your organisation in reverse domain name notation. For example, given the `crossingthestreams.io` domain, the organisation would be specified as `io.crossingthestreams`. <android_language> is either `java` or `kotlin` and <ios_language> is either `objc` or `swift`. The tooling will generate a `widget_test.dart` file within the `test` folder that can be deleted. Successfully executing all of the steps would create an application with the desired application name, bundle identifier and create the appropriate Android and iOS project files. From there you should be able to run the application. You can then the `pubspec.yaml` to your liking (e.g. to update the dependencies). Note that the templates have unit tests, widget tests and integration tests included. Therefore, if you make changes then these tests may need to be updated to stop them from failing.

## Contributions

Feel free to submit PRs to share templates that you feel would be useful to others. A short checklist to things to do are

- Add information to the template's readme
- Include unit tests, widget test and integration tests
- Update the `.cirrus.yml` file to include your template
- Keep the original .gitignore file generated by the `flutter create` command. This would ensure that when a template is used to create an application, the relevent Android and iOS projects can by checked into source control
- Ensure that the steps described above for creating an application from a template works with the template you're submitting

The `material_bottomnavigation_provider_mobx` folder can be referred to in order mimic what has been done there when submitting a new template
