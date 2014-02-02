ai-memo
=======

AIM-057

To quote fogus here:
  http://blog.fogus.me/2014/01/27/timothy-hart-rest-in-peace/

"On January 20, 2014 the world lost a hacker named Timothy Hart. Hart
was not just any hacker — he was a hacker of the highest order. If
you’ve read more than three books on Lisp then you might have seen his
name pop up here and there. If not, then you’ve definitely felt his
influence."

The scan of Timothy Hart's memo on macros is difficult to read.
I decided to transcribe it while reading. I was tempted to
reformat the code, but didn't do it within my transcript.

The stash macro:

MACRO ((
(STASH (LAMBDA (FORM)(LIST (QUOTE SETQ)(CADAR FORM)(LIST (CONS (CADR FORM)
(CADAR FORM))) )))
))

seems to have some bugs. CADAR should maybe be CADDR, and CONS should
maybe be quoted. I searched quickly for a sanity check and found a
message in by Kaz Kylheke in comp.lang.lisp 2009-06-26 that says as
much.
