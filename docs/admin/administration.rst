========================
 Running a richard site
========================

.. Note::

   The information in this chapter is likely to change as we spend
   more time on the admin side of things.


Changing the theme/style/look-n-feel
====================================

Override the CSS, JS and templates.

.. todo:: flesh out how to override css, js and templates


Using the admin tool
====================

1. Enter the admin are of your site. This is often the url for your
   site plus ``/admin/``.

   e.g. For a richard installation at `<http://example.com/>`_, the
   admin would be at `<http://example.com/admin/>`_.

   .. Note::

      If you want a link to the admin page from the fron page of your
      site, just modify your site templates.

2. If you haven't logged into the admin, you will need to do so
   now. Use the superuser account you created when installing richard.

Once in the admin tool, you have access to all the data on the site
including site news, site-wide notifications, videos, categories,
tags, and speakers.


Adding videos
=============

1. Enter the admin tool.

2. Once logged in, click on `Videos` on the left side.

3. Click on `Add Video` in the upper right hand side.

4. Fill out the information to add the video.

   Keep it in DRAFT mode until you're done with it. This keeps it from
   showing up in any of the video lists, but you can still see the
   video if you go directly to its page.

   Make sure to `save and continue editing` from time to time. After
   doing that, you can click on `View on site` in the upper right hand
   corner and see what the video looks like on the site.


Editing videos
==============

1. Enter the admin tool.

2. Once logged in, click on `Videos` on the left side.

3. Find the video you want to edit and then click on the video to edit
   it.

   Make sure to `save and continue editing` from time to time. After
   doing that, you can click on `View on site` in the upper right hand
   corner and see what the video looks like on the site.

.. Note::

   If you're already logged in as an admin, every video page on the
   site will have an `edit` link at the top of the metadata. If you
   click that, it'll bring you directly to the video edit page in the
   admin.


Removing videos
===============

1. Enter the admin tool.

2. Once logged in, click on `Videos` on the left side.

3. Find the video you want to delete and then click on the video to go
   to the edit screen.

4. Click on the `delete` link in the top left.

.. Warning::

   Deleting videos is currently permanent! There's no way to undo this
   action.


Importing a batch of videos
===========================

There is currently no way to import a batch of videos all at once.

You could write a script that runs on your server that accesses the
model objects directly. That's what I've been doing so far. That
requires Python/Django chops.


Updating the search index
=========================

Updating the index is a manual process. It's possible we could update the
index as data is changed, but richard is currently not set up that way.

Do this to update the index::

    ./manage.py rebuild_index

You probably want to either put this in a cron job or run it after
making any data changes.

.. Warning::

   This deletes the index, then rebuilds it. Thus there will be a
   period of time during which search on your site will kind of suck.
