# 🚧 Task affinities

😁 $$a = b$$ 🍉 

Task affinities indicate which task an `Activity` prefers to belong to when that `Activity` instance is launched. By default each `Activity` belongs to the app that launched it. An `Activity` from outside an app launched with an implicit `Intent` belongs to the app that sent the implicit `Intent`.

To define a task affinity, add the `android:taskAffinity` attribute to the `<activity>` element in the `AndroidManifest.xml` file. The default task affinity is the package name for the app \(declared in `<manifest>`\). The new task name should be unique and different from the package name. This example uses `"com.example.android.myapp.newtask"` for the affinity name.

{% tabs %}
{% tab title="XML/HTML/SVG" %}
```markup
<activity
   android:name=".SecondActivity"
   android:label="@string/activity2_name"
   android:parentActivityName=".MainActivity"
   android:taskAffinity="com.example.android.myapp.newtask">
   <!-- More attributes ... -->
</activity>
```
{% endtab %}

{% tab title="hlk" %}
## hoho

```aspnet
ljşl
```
{% endtab %}
{% endtabs %}

Task affinities are often used with the `singleTask` launch mode or the [`FLAG_ACTIVITY_NEW_TASK`](https://developer.android.com/reference/android/content/Intent.html#FLAG_ACTIVITY_NEW_TASK) `Intent` flag to place a new `Activity` in its own named task. If the new task already exists, the `Intent` is routed to that task and that affinity.

Another use of task affinities is reparenting, which enables a task to move from the `Activity` in which it was launched to the `Activity` it has an affinity for. To enable task reparenting, add a task affinity attribute to the `<activity>` element and set `android:allowTaskReparenting` to true.

```markup
<activity
   android:name=".SecondActivity"
   android:label="@string/activity2_name"
   android:parentActivityName=".MainActivity"
   android:taskAffinity="com.example.android.myapp.newtask"
   android:allowTaskReparenting="true" >
   <!-- More attributes ... -->
</activity>
```

