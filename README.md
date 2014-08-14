## Comment Upload (Drupal 7)

This is a upgrade path for Comment Upload module (from D6 to D7) and File field formatter that emulates Comment Upload representation of attached files.

The upgrade path is originally based on the module https://www.drupal.org/node/554986#comment-6582290 but contains several significant improvements:

1) Table names now uses brackets for example {node} to support table prefixes.
2) Prevented constrain violation on passing duplicate uri in {file_managed}.uri field.
3) All Comment Upload attachment is converted to File fields instead of images that allows us to display files as well as images.
4) Comment Upload formatter is set for all converted fields.
5) A bit improved code style.

The module also provides Comment Upload formatter that emulates D6 attachment representation (images as thumbnails, files as table).

### UPGRADE FROM D6

1) After core upgrade enable remove old comment_upload module and download this one https://github.com/konstantin-komelin/comment_upload.git
2) Enable new Comment Upload module.
3) Run update.php and update database (this step may take significant time, make sure your PHP max_execution_time value is high enough).
4) Choose a common image style for all Comment Upload images admin/config/media/comment_upload
5) Test your Comment Upload fields

### USE AS A FILE FIELD FORMATTER

1) Create a File field that belongs to an entity.
2) Choose Comment Upload formatter in the field display settings.
3) Enjoy your Comment-Upload-like attachments (images as thumbnails, files as a table).
