SixArm.com » Postfix » Checks for spam blocking

Postfix checks for spam blocking.

Example use in main.cf

  header_checks = regexp:/etc/postfix/custom/header_checks.txt
  mime_header_checks = regexp:/etc/postfix/custom/mime_header_checks.txt
  body_checks = regexp:/etc/postfix/custom/body_checks.txt

To test the expressions:

  postmap -q - pcre:header_checks.txt < msg
  postmap -q - pcre:body_checks.txt < msg

Also see the repo sixarm_postfix_scripts which have shortcut scripts:

  ./postfix-header-checks msg
  ./postfix-body-checks msg

See the postfix regular expression documentation:
http://www.postfix.org/pcre_table.5.html

