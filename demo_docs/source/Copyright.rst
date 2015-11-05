:orphan: True



.. _Copyright:

=========
Copyright
=========

Here we go.


Globalcontext of StandaloneHTMLBuilder
======================================

.. code-block:: python

   class StandaloneHTMLBuilder(Builder):
      """
      Builds standalone HTML docs.
      """
      def prepare_writing(self, docnames):

         self.globalcontext = dict(
            embedded = self.embedded,
            project = self.config.project,
            release = self.config.release,
            version = self.config.version,
            last_updated = self.last_updated,
            copyright = self.config.copyright,
            master_doc = self.config.master_doc,
            use_opensearch = self.config.html_use_opensearch,
            docstitle = self.config.html_title,
            shorttitle = self.config.html_short_title,
            show_copyright = self.config.html_show_copyright,
            show_sphinx = self.config.html_show_sphinx,
            has_source = self.config.html_copy_source,
            show_source = self.config.html_show_sourcelink,
            file_suffix = self.out_suffix,
            script_files = self.script_files,
            language = self.config.language,
            css_files = self.css_files,
            sphinx_version = __display_version__,
            style = stylename,
            rellinks = rellinks,
            builder = self.name,
            parents = [],
            logo = logo,
            favicon = favicon,
         )
         if self.theme:
            self.globalcontext.update(
               ('theme_' + key, val) for (key, val) in
               iteritems(self.theme.get_options(self.theme_options)))
         self.globalcontext.update(self.config.html_context)
