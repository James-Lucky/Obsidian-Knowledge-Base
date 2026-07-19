Firefox Bookmark Background Opening Fix
======================================

Issue:
- Ctrl + Click on bookmarks was opening the bookmark immediately in the foreground tab.
- Expected behavior: Keep the current tab active and open bookmarks in background tabs (similar to Chrome).

Required about:config Settings:

1. browser.tabs.loadBookmarksInBackground
   Value: true
   Purpose:
   - Opens bookmarks in background tabs when using Ctrl + Click.

2. browser.tabs.loadInBackground
   Value: true
   Purpose:
   - Opens links and tabs in the background instead of switching to them immediately.

Optional (Not the actual fix in my case):

3. browser.bookmarks.openInTabClosesMenu
   Value: false
   Purpose:
   - Keeps the bookmarks menu open after opening a bookmark.
   - Does NOT control background opening behavior.

Final Result:
- Ctrl + Click now behaves like Chrome.
- Multiple bookmarks can be opened in background tabs.
- The current tab remains unchanged.

Note:
- The main setting responsible for fixing the issue was:

  browser.tabs.loadBookmarksInBackground = true