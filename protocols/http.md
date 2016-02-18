# HTTP
## htpasswd on a proxy server over another authorized service
(2016/02/18)
So we're running nginx with htpasswd authorization which then proxies to some
Atlassian tools (bitbucket and JIRA), only a single user login worked intially, and the other logins
would respond with garbage from the atlassian tool URLs, it turned out that the
user that worked, only worked because the htpasswd details were the same as
those on the Atlassian tools, whereas the other users in htpasswd did not have a
corresponding login for the tools (i.e. same user and same password) so the
login wasn't working properly.

TLDR: If you're using htpasswd in front of a service that uses HTTP
authorization headers, make sure the htpasswd users have corresponding users in
your authorized service.
