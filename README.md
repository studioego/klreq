# Requirements for Hangul Text Layout and Typography (klreq)

###Documents
- [Editor's copy](https://w3c.github.io/klreq/)
- [WG Note](https://www.w3.org/TR/klreq/)

The document contains both English and Korean versions of the text. Use the buttons at the top of the document window to select a single-language view.

###Feedback
Please use the [GitHub issue list](https://github.com/w3c/klreq/issues) to send feedback about this document.

###Following
To follow the work, you can 'Watch' this repository using the control above, or subscribe to the [public-i18n-cjk](https://lists.w3.org/Archives/Public/public-i18n-cjk/) mailing list, which is notified once a day about changes to the repo. The [www-international](https://lists.w3.org/Archives/Public/www-international/) list is also notified daily. (Please use github issues rather than the mailing list to send feedback.)

For archived issues, predating github, see the disused [issue tracker](http://www.w3.org/International/track/products/42).


###Contributing

All contributors should read and agree with [CONTRIBUTING.md](https://github.com/w3c/klreq/blob/gh-pages/CONTRIBUTING.md).

There is currently no Korean Layout Task Force.

Editors should be familiar with and use the following:

- [Github guidelines for working with i18n documents](http://w3c.github.io/i18n-activity/guidelines/github)
- [Editorial guidelines for working with i18n documents](http://w3c.github.io/i18n-activity/guidelines/editing)


##Additional information for editors 

Combining the English and Korean text in one document makes it much easier to develop and maintain content in both languages in parallel. Note that the English version will be the authoritative version, since it is more widely accessible to developers around the world.


###Creating or modifying content###

When creating new content, you should always create markup for both Korean and English versions.

Example:
```
<p data-lang="en">Korean typography experts.</p>
<p data-lang="ko">한국어 텍스트 폰트 전문가</p>
```


If you are able to create text in both English and Korean, please do so. If you are only able to create text in one language, still create the dual structure in markup, but put the same text in both places. Then add `class="translateme"` to the text that needs translation.

Example:
```
<p data-lang="en" class="translateme">한국어 텍스트 폰트 전문가</p>
<p data-lang="ko">한국어 텍스트 폰트 전문가</p>
```

If you change existing text, and if that change requires a change in the parallel translation but you are unable to do so, add `class="translateme"` to the text that needs to be updated.

When text highlighted by the translateme class is updated, and matches the recent changes in the other language, the class should be removed.


###Markup tips###

Here are some tips on how to maintain the parallel language structure in markup. The principles in these example approaches should be extended to other markup as needed.

The english text should always come before the korean text.

List elements need `p` elements inside them:
```
<li>
<p data-lang="en">Korean typography experts</p>
<p data-lang="en">한국어 텍스트 폰트 전문가</p>
</li>
```

Headings should use spans for en and ko versions, and there should be a line break between spans.
```
<h2><span data-lang="en">Korean typography experts</span>
<span data-lang="ko">한국어 텍스트 폰트 전문가</span></h2>
```

Ids should go on section elements, not `hx` elements.
```
<section id="h_my_heading">
<h2><span data-lang="ko">Korean typography experts</span>
<span data-lang="en">한국어 텍스트 폰트 전문가</span></h2>
```

Ids on `dfn` elements should start with `xxdef`, where xx is either en or ko.
```
<p data-lang="en">Korean <dfn id="endef_term">typography</dfn> experts.</p>
<p data-lang="ko">한국어 <dfn id="kodef_term">텍스트</dfn> 폰트 전문가.</p>
```

Figcaptions should use spans for the different language versions.
```
<figure>
Main figure content here.
<figcaption><span data-lang="en">Korean typography experts</span>
<span data-lang="ko">한국어 텍스트 폰트 전문가</span></figcaption>
```

Use the following markup for Unicode codepoint names:
```
<span class="uname">U+3002 IDEOGRAPHIC FULL STOP</span> [。]
```

For additional ideas about markup and styling in Internationalization Activity documents, especially wrt inline markup conventions, see
http://www.w3.org/International/docs/styleguide


###Pre-publication edits##

the following edits should be made to the snapshot of the file that will be published.

[1] remove  onload="addLangAttrs();" from the body tag

[2] convert the contents of the h1 tag to the following:
```
<span data-lang="en">Requirements for Hangul Text Layout and Typography</span><br/>
  <span data-lang="ko" lang="ko">한국어 텍스트 레이아웃 및 타이포그래피를 위한 요구사항</span>
```

[3] in the SOTD, change the link on "latest dated version in /TR" to point to the location of the document that is about to be published

(the same change should be made to the respec file)
