# 🔤 Naming Conventions

## Naming conventions <a href="#7a56" id="7a56"></a>

**UpperCamelCase**: For Classes, Enumerations, and Typedefs.

<table><thead><tr><th width="384">Good</th><th>Bad</th></tr></thead><tbody><tr><td><code>class HomeLayout {}</code></td><td><code>class homeLayout {}</code></td></tr><tr><td><p><code>enum IntegrationEnv {</code></p><p>  <code>dev,</code></p><p>  <code>pro,</code></p><p><code>}</code></p></td><td><p><code>enum integration_env {</code></p><p>  <code>dev,</code></p><p>  <code>pro,</code></p><p><code>}</code></p></td></tr><tr><td><code>typedef NaviAction = void Function();</code></td><td><code>typedef naviaction = void Function();</code></td></tr></tbody></table>



**snake\_case:** Libraries, packages, directories, and file names.

<table><thead><tr><th width="384">Good</th><th>Bad</th></tr></thead><tbody><tr><td><code>library appflowy_calendar;</code></td><td><code>library AppFlowy_Calendar;</code></td></tr><tr><td><code>import 'package:protobuf/protobuf.dart';</code></td><td><code>import 'package:protobuf/Protobuf.Dart';</code></td></tr><tr><td><code>appflowy_calendar_block.dart</code></td><td>A<code>ppflowyCalendar_block.dart</code></td></tr></tbody></table>



**lowerCamelCase:** Variables, constants, and parameters.

<table><thead><tr><th width="384">Good</th><th>Bad</th></tr></thead><tbody><tr><td><code>let mut item;</code></td><td><code>let mut Item;</code></td></tr><tr><td><code>const testValue = 14.28;</code></td><td><code>const test_value = 14.28;</code></td></tr><tr><td><code>final urlScheme = RegExp(‘^([a-z]+):’);</code></td><td><code>final Url_Scheme = RegExp(‘^([a-z]+):’);</code></td></tr><tr><td><code>void sum(int testValue) { ... }</code></td><td><code>void sum_of(int test_value) { ... }</code></td></tr></tbody></table>
