# Add a custom linkification filter

If you are an administrator of a Zulip organization, you can add custom
linkification filters to your organization that automatically turn phrases in
messages into links to other pages.

1. Click the cog (![cog](/static/images/help/cog.png)) in the upper right corner
of the right sidebar.

2. Select **Administration** from the dropdown menu that appears.

    ![Administration dropdown](/static/images/help/administration.png)

3. Upon clicking **Administration**, your view will be replaced with the
**Administration** page. You will be located on the **Organization settings**
tab by default.

    ![Administration page](/static/images/help/admin-window.png)

4. Scroll down to the **Custom linkification filters** section located below the
**Custom emoji** section.

    ![Custom linkification filters](/static/images/help/custom-link-section.png)


5. In the green section labeled **Add a New Filter**, find the **Regular expression**
and **URL format string** fields.

    * In the **Regular expression** field, enter a
[regular expression](http://www.regular-expressions.info) that searches and
identifies the phrases you want to linkify.

        ![Regular expression](/static/images/help/filter-regex.png)

        For example, if you want to linkify any numeric phrase that begins with
a `#`, you could use the regular expression `#(?P<id>[0-9]+)` to find those
phrases, where `id` is the variable that represents the phrase found by the
search.

        Please note that all regular expressions used for custom linkification
filters in your organization must be unique. In addition, the regular expression
you enter must have a variable that gets identified by the URL format string.

    * In the **URL format string** field, insert a URL that includes the regular
expression variable you specified in the **Regular expression** field. The URL
format string must be in the format of `https://example.com/%(\w+)s`.

        ![URL format string](/static/images/help/url-format-string.png)

        For example, if you want to use the variable `id` found by your regular
expression to link to a corresponding GitHub pull request on the `zulip/zulip`
repository, you could use the URL format string
`https://github.com/zulip/zulip/pull/%(id)s`.

6. After filling out the **Regular expression** and **URL format string**
fields, click the blue **Add filter** button to add your custom linkification
filter to your Zulip organization.

    ![Add filter](/static/images/help/add-filter.png)

7. Upon clicking the **Add filter** button, you will receive a notification
labeled **Custom filter added!** in the **Custom linkification filters**
section, confirming the success of the addition of your custom linkification
filter to your organization.

    ![Custom linkification filter success](/static/images/help/custom-filter-success.png)

    The filter's information and settings will also be displayed above the **Add a New Filter**
section. You can choose to delete any custom linkification filters in your
organization through this panel by pressing the red **Delete** button next to
the filter you want to delete.

8. Users in your organization can now use your custom linkification filter in
their messages.

    ![Custom linkification filter demo](/static/images/help/custom-filter-demo.png)
