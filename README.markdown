# JsonHelper
How to use 
Add it to your build.gradle :

allprojects {
    repositories {
        google()
        jcenter()
*       maven { url "https://jitpack.io"}
    }
}

and:

## app.gradle

dependencies {
 *   implementation fileTree(dir: 'libs', include: ['*.jar'])
 *   implementation 'androidx.appcompat:appcompat:1.0.2'
 *   implementation 'androidx.constraintlayout:constraintlayout:1.1.3'
 *   ### implementation 'com.github.one2z3ro:JsonHelper:v0.3' ###
 *   testImplementation 'junit:junit:4.12'
 *   androidTestImplementation 'androidx.test.ext:junit:1.1.0'
 *   androidTestImplementation 'androidx.test.espresso:espresso-core:3.1.1'
}

    
# Usage
//        UrlArrayUtils.setContext(this)
//                .setCallbackHandler(this)
//                .setType(Minion.class)
//                .urlRequest("http://nully000-001-site1.atempurl.com/hexo_data.json");

        UrlSingleUtils.setContext(this)
                .setCallbackHandler(this)
                .setType(Request.class)
                .urlRequest("https://api.edamam.com/search?q=beef&app_id=7b790015&app_key=15264eee8cbce932a6ab6af4a739b7c0&from=0&to=30");

# implement callback IUrlRequestHandler
    @Override
    public <T> List<T> onComplete(List<T> objs) {
        for (Object l : objs) {
            Log.d("UrlUtils", ((Minion) l).Name);
        }
        return null;
    }

check lib state :
* https://jitpack.io/com/github/0nully/JsonHelper/VERSION-NUMBER/build.log
