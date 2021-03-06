===
OCR
===

Because OCR is an intensive operation, documents are queued for OCR for
later handling, the amount of documents processed in parallel is
controlled by the :setting:`OCR_NODE_CONCURRENT_EXECUTION` configuration
option.  Ideally the machine serving **Mayan EDMS** should disable OCR 
processing by settings this options to 0, with other machines or cloud
instances then connected to the same database doing the OCR processing.
The document is checked to see if there are text parsers available, is
no parser is available for that file type then the document is passed
to tesseract page by page and the results stored per page, this is to
keep the page image in sync with the transcribed text.  However when
viewing the document in the details tab all the pages text are
concatenated and shown to the user. Setting the :setting:`OCR_AUTOMATIC_OCR`
option to ``True`` would cause all newly uploaded documents to be
queued automatically for OCR.
