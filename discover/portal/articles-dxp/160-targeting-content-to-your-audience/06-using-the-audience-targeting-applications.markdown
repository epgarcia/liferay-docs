# Using the Audience Targeting Applications [](id=using-the-audience-targeting-applications)

Audience Targeting includes some instanceable applications which can be added 
to any portal page:

- Campaign Content Display
- User Segment Content Display
- User Segment Content List

All of these applications support Application Display Templates (ADTs), and any 
of Liferay Portal's out-of-the-box Asset Publisher ADTs can actually be re-used 
for these Audience Targeting applications.

## User Segment Content Display [](id=user-segment-content-display)

User Segment Content Display displays content to users based on the user 
segments that the user belongs to. Administrators can specify multiple rules 
according to the following format:

- If the user \[belongs|does not belong\] to \[any|all\] of the following user
  segments [specify a list of user segments], then display this content:
  \[specify a specific asset\].
 
You can specify any number of *if* clauses when configuring the User Segment
Content Display application's rules. However, an *otherwise* clause always
follows the last *if* clause so that the application knows what to display if
the user doesn't match any user segments. *Don't display anything* is an option
for the *otherwise* clause.

![Figure 1: You can configure the User Segment Content Display application to display content according to rules that you define in the application's configuration window.](../../images-dxp/user-segment-content-display-config.png)

For example, you can add a User Segment Content Display application to a page 
and configure the following rules for it:

- If the user *belongs* to *any* of the following user segments: *Tennis fans*,
  then display this content: *tennis_picture.jpg*.
- If the user *belongs* to *any* of the following user segments: 
  *Basketball fans*, then display this content: *basketball_picture.jpg*.
- If the user *belongs* to *any* of the following user segments: *Soccer*, then
  display this content: *soccer_picture.jpg*.
- Otherwise, *Don't display anything*.

Once the application has been configured this way, users (even guest users) 
will see a different image based on the user segment to which they belong. The 
application won't even be visible to a user if the user doesn't belong to any 
of the configured user segments.

![Figure 2: In the User Segment Content Display application, site administrators can preview the various assets that have been configured to be displayed to different user segments.](../../images-dxp/audience-targeting-uscd.png)

Administrators can preview the various assets that have been configured for 
different user segments.

## Campaign Content Display [](id=campaign-content-display)

Campaign Content Display is similar to the User Segment Content Display except 
that instead of displaying assets based on the user segments to which a user 
belongs, it displays an asset based on the campaigns that a user matches. 
However, the Campaign Content Display application's display rules are simpler 
than those of the User Segment Content Display application. You can specify 
multiple rules for the Campaign Content Display application according to the 
following format:

- If the user belongs to this campaign: [select a campaign], then display this
  content: \[specify a specific asset\].

As with the User Segment Content Display, you can specify any number of *if* 
clauses when configuring the Campaign Content Display application. An 
*otherwise* clause always follows the last *if*. These rules cannot be ordered 
manually as they can with the User Segment Content Display application. The 
order of the rules is based on the priority of the campaigns.

![Figure 4: The rules for configuring the Campaign Content Display application to display content are similar to the rules of the User Segment Content Display application, but simpler.](../../images-dxp/campaign-content-display-config.png)

For example, if you created two campaigns called *World Cup* and *Stanley Cup*, 
designed to target users who are interested in the World Cup of soccer and the 
Stanley Cup of hockey. You could add a Campaign Content Display application to 
a page and configure it with the following rules:

- If the user belongs to this campaign: *World Cup*, then display this content:
  *soccer-ball.jpg*.
- If the user belongs to this campaign: *Stanley Cup*, then display this
  content: *hockey-.png*.
- Otherwise, display this content: *generic-sports-jersey.jpg*

Once a Campaign Content Display has been added to a page and been configured 
this way, portal users matching the World Cup campaign will see the soccer 
image. Users matching the Stanley cup campaign will see the hockey image. Users 
who don't match either will see the default image. Of course, once a campaign has ended, no users will match that campaign. Once all campaigns have ended, all users will see the default image.

+$$$

**Note:** When Audience Targeting is enabled with a large number of rules,
tracking actions, and reports, you may need to adjust some JVM parameters of
your server for optimal performance.

$$$

The Campaign Content Display application, like the User Segment Content Display
application, allows site administrators to preview the different assets that
will be displayed for different campaigns.

## Asset Publisher

The Asset Publisher is part of Liferay's Web Experience Management suite, but it
serves an important function with Audience Targeting. When Audience Targeting is
installed, the Asset Publisher gains an additional configuration option: *User
Segments Filter*. The User Segments Filter enables the Asset Publisher to
display content to users based on their User Segments. In this way, the Asset
Publisher provides one of the most important pieces of Audience Targeting:
a means of displaying content based on your user segments and campaigns.

When *User Segments Filter* is activated, the only assets that are displayed are
those that match the filters configured in the portlet and are categorized under
any of the user segments for the current user. Assets not categorized with User
Segments don't appear in any Asset Publisher with the *User Segments Filter*
enabled.

Next you'll learn how to simulate your user segments and campaigns.
