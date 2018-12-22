[![](https://jitpack.io/v/arefbhrn/MaskedEditText.svg)](https://jitpack.io/#arefbhrn/MaskedEditText)

Masked EditText
==============================

A library to achieve masked TextView for both RTL and LTR texts.

![MaskedEditText - the library for masked input of phone numbers, social security numbers and so on for Android](https://raw.githubusercontent.com/egslava/edittext-mask/master/publish/README.gif)

This project derives from [egslava/edittext-mask](https://github.com/egslava/edittext-mask), but it's been adapted for `AndroidX`:

1. filter allowed chars
2. filter denied chars
3. use chars from mask in input (ex: use digit '7' in the '+7(XXX)XXX-XX-XX' pattern)
4. keep hints even when user started typing

So it allows you to use masks for phones, urls, etc.

Enjoy!

*********************************

Installation
===============================

Gradle

```
dependencies {
    implementation 'com.github.arefbhrn:MaskedEditText:1.0.0'
}
```

Usage
===========================

Add `xmlns:app="http://schemas.android.com/apk/res-auto"` to your layout xml root:

    <com.arefbhrn.maskededittext.MaskedEditText
        android:id="@+id/phone_input"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:inputType="phone"
        android:typeface="monospace"
        android:hint="1234567890"
        app:allowed_chars="1234567890"
        app:mask="+44(###)###-##-##"
        app:keep_hint="true" />

Where `mask` is the input mask you want and '#' is an editable position (will be replaced by a whitespace on screen).

You can optionally set the representation character (in case you don't want to use '#'):

    <com.arefbhrn.maskededittext.MaskedEditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        mask:mask="ccc.ccc.ccc-cc"
        mask:char_representation="c" />

You can also use the it programmatically:

	MaskedEditText editText = (MaskedEditText) findViewById(R.id.my_edit_text)

	// Setting the representation character to '$'
	editText.setCharRepresentation('$');

	// Get the representation character
	editText.getCharRepresentation();

	// Setting the mask
	editText.setMask("##/##/####");

	// Logging the mask
	editText.getMask();

	// Get typed text without mask chars
	editText.getRawText();

	// Keep hint showing
	editText.setKeepHint(true);

Contact me
===========================

If you have a better idea or way on this project, please let me know, thanks :)

[Email](mailto:arefprivate@gmail.com)

License
===========================

This project is licensed under the Apache 2.0 License - see the [LICENSE.md](LICENSE.md) file for details
