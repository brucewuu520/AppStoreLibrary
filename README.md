## AppStore Library
This library make easy to use AppStore app' features.

### Features
- Check store app is installed.
- Open app within store app.
- Search apps by publisher within store app.
- Search apps within store app.

### AppStore
- Play AppStore
- Amazon AppStore
- T Store
- Naver AppStore

## Gradle & Maven
Gradle
```groovy
    dependencies {
    	compile 'net.sjava.appstore:library:1.0.1@aar'
    }
```

Maven
```xml
    <dependency>
     <groupId>net.sjava.appstore</groupId>
     <artifactId>library</artifactId>
     <version>1.0.1</version>
    </dependency>
```
## Usage

```java
	private void initPlayAppStore() {
		Button btn01 = (Button)findViewById(R.id.play_button_01);
		Button btn02 = (Button)findViewById(R.id.play_button_02);
		Button btn03 = (Button)findViewById(R.id.play_button_03);
		Button btn04 = (Button)findViewById(R.id.play_button_04);

		btn01.setOnClickListener(new View.OnClickListener() {
			@Override
			public void onClick(View v) {
				appStore = PlayAppStore.newInstance();
				Toast.makeText(ctx, "설치 여부 : " + appStore.isInstalled(ctx), Toast.LENGTH_SHORT).show();
			}
		});

		btn02.setOnClickListener(new View.OnClickListener() {
			@Override
			public void onClick(View v) {
				appStore = PlayAppStore.newInstance();
				appStore.openApp(ctx, "com.google.android.gm");
			}
		});

		btn03.setOnClickListener(new View.OnClickListener() {
			@Override
			public void onClick(View v) {
				publisherAppOpener = PlayAppStore.newInstance();
				publisherAppOpener.openPublisherApps(ctx, "Google Inc.");
			}
		});

		btn04.setOnClickListener(new View.OnClickListener() {
			@Override
			public void onClick(View v) {
				appStore = PlayAppStore.newInstance();
				appStore.searchApp(ctx, "gmail");
			}
		});
	}
```

## License

Copyright 2015 Justin Song

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

