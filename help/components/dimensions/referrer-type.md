---
title: Referrer type
description: The type of referrer, depending on where the visitor came from.
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
---
# Referrer type

The 'Referrer type' dimension reports which generic channels visitors clicked through to arrive at your site. Adobe maintains the rules for each dimension item, unlike [Marketing channels](marketing-channel.md), where your organization maintains rules for each channel.

## Populate this dimension with data

This dimension references multiple lookup tables internal to Adobe. Each value is based on the [referrer](referrer.md) of the hit, which depends on [Internal URL filters](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). Make sure that the referrer dimension and internal URL filters are configured correctly.

## Dimension items

Dimension items include the type of referrer of the hit. Specific values include the following:

* **Typed/Bookmarked**: No referrer data exists for the hit.
* **Search engines**: The referrer came from a recognized search engine that includes a keyword query string.
* **Social networks:**: Referrer data belonged to an Adobe-recognized social network.
* **Other web sites**: Referrer data did not belong to a search engine or social network that Adobe recognizes.
* **Hard drive**: Referrer originated from a local copy of a web page on the visitor's hard drive.
* **Email**: Referrer originated from a URL with a protocol of `imap://` or `mail://`. Does not include online email services, as these typically use `https://` protocol.

### Social networks

The following list references the 'Social networks' lookup table that Adobe uses. Adobe provides this list as a courtesy to Adobe Analytics customers. If you would like to recommend that Adobe adds a domain to this list, have a support delegate in your organization contact Customer Care.

>[!NOTE]
>
>This list is different than the default list of social networks in [Marketing channel processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

* `12seconds.tv`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `answers.yahoo.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blog.seesaa.jp`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `delicious.com`
* `deviantart.com`
* `digg.com`
* `diigo.com`
* `disqus.com`
* `draugiem.lv`
* `facebook.com`
* `faceparty.com`
* `fc2.com`
* `flickr.com`
* `flixster.com`
* `fotolog.com`
* `foursquare.com`
* `friendfeed.com`
* `friendsreunited.com`
* `friendsreunited.co.uk`
* `friendster.com`
* `fubar.com`
* `gaiaonline.com`
* `geni.com`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `hi5.com` 
* `hotnews.infoseek.co.jp`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `jp.myspace.com`
* `kaixin001.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `linkedin.com`
* `livejournal.com`
* `lnkd.in`
* `meetup.com`
* `me2day.net`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `mp.weixin.qq.com`
* `multiply.com`
* `mumsnet.com`
* `myheritage.com`
* `mylife.com`
* `myspace.com`
* `myyearbook.com`
* `nasza-klasa.pl`
* `matome.naver.jp`
* `netlog.com`
* `nettby.no`
* `netvibes.com`
* `nextdoor.com`
* `nicovideo.jp`
* `ning.com`
* `odnoklassniki.ru`
* `ok.ru`
* `orkut.com`
* `pakila.jp`
* `photobucket.com`
* `pinterest.com`
* `pinterest.co.uk`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `reddit.com`
* `renren.com`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `snapchat.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.163.com`
* `t.co`
* `t.hexun.com`
* `t.people.com.cn`
* `t.qq.com`
* `t.sina.com.cn`
* `t.sohu.com`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `tiktok.com`
* `toutiao.com`
* `tripit.com`
* `trombi.com`
* `trytrend.jp`
* `tuenti.com`
* `tumblr.com`
* `twine.com`
* `twitter.com`
* `uhuru.jp`
* `viadeo.com`
* `vimeo.com`
* `vk.com`
* `wayn.com`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `xanga.com`
* `xing.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yozm.daum.net`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### Search engines in the 'Other websites' dimension item

When you view specific domains in the 'Referrer type' dimension, there can be domains that you would expect under 'Search engines' listed instead under 'Other web sites'. For example, you might see `'google.com'` under 'Other web sites'.

* **Search engine domains in the 'Search engines' dimension item**: The referrer met all criteria to classify as a search engine by Adobe. The referring domain is a valid search engine, *and* the referring URL contains a keyword query string parameter.
* **Search engine domains in the 'Other websites' dimension item**: The referring URL did not meet all criteria to classify as a search engine. Common examples include subdomains dedicated to other features besides search. For example, `mail.google.com` or `autos.yahoo.com` are not search engines, but reside on a top-level domain commonly associated with search. These subdomains do not include a keyword query string, which is why they are included under 'Other websites' instead of 'Search engines'.
