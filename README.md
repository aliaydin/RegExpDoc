# RegExpDoc
## Regular Expression notları

Phpstorm içinde regexp ile stringi parçalar halinde alıp düzenlemek gerekti.

**Örnek;**

`<li><img src="assets/images/resim.png" alt="Resim"></li>`

yukarıdaki kodu

`<li><img src="{{ assets('images/site/resim.png') }}></li>`

olarak değiştirmek istiyoruz.

regexp : `(assets/)(.*)(/.*)("\salt)`

her bir parantez bir grup olarak yakalanır ve sırasıyla `$1,$2...$n` ile erişilir.

replace alanı : `{{ asset('images/site/$2$3') }}" alt`


**Örnek;**

`<?php include 'includes/file.php' ?>`
istenen
`@include('layouts.site.file')`

regex : `(<\?php include 'includes/)(.*)(\.php' \?>)`

replace string : `@include('layouts.site.$2')`


**Örnek;**

`[someKey]`
istenen
`['someKey']`

regex : `(\[)(.*)(\]) //'[' regexpte özel karakter olduğu için '\' kullandık `

replace string : `['$2']`
