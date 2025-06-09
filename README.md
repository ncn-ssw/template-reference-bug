# Template Reference Bug Replication

This is a minimum replication of a bug.

A reference field has been added to the Content template at
https://github.com/ncn-ssw/template-reference-bug/blob/66a57eb29cdb55f788333160835fb89f339e3b29/components/blocks/content.tsx#L39

To trigger the bug.

1. Run `npm init`
2. Run `npm dev`
3. Go to http://localhost:3000/admin/index.html#/~/about
4. Open the "Content" section
5. In the field "Tag1" select "markdown"
6. Click "Save"
7. Go to "/content/pages/about.mdx" and you will see that "- tag1: content/tags/markdown.mdx" has been added
8. Go to http://localhost:3000/admin/index.html#/collections/tag/~
9. Delete markdown (content/tags/markdown.mdx)
10. Go to "/content/posts/learning-about-markdown.mdx" and you will see that a reference to "content/tags/markdown.mdx" has been removed
11. Go to "/content/pages/about.mdx" and you will see that "- tag1: content/tags/markdown.mdx" remains

The reference to "content/tags/markdown.mdx" should also be removed from "/content/pages/about.mdx".

## LICENSE

Licensed under the [Apache 2.0 license](./LICENSE).
