## Welcome to GitHub Pages


/**
 * Definition for a binary tree node.
 * function TreeNode(key) {
 *     this.val = key;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number}
 */
var rob = function(root) {
  var dfs = function (node) {
    if (node === null) {
      return [null, null];
    }
    var left = dfs(node.left);
    var right = dfs(node.right);
    var res = [];
    res[0] = left[1] + right[1] + node.key;
    res[1] = Math.max(left[0], left[1]) + Math.max(right[0], right[1]);
    return res;
  };

  var num = dfs(root);
  return Math.max(num[0], num[1]);
};

var rob = require('../rob3');
var BinarySearchTree = require('../../Tree/BinarySearchTree');

test('rob3', function () {
  var binarySearchTree = new BinarySearchTree();

  binarySearchTree.insert(11);
  binarySearchTree.insert(7);
  binarySearchTree.insert(13);
  binarySearchTree.insert(5);
  binarySearchTree.insert(3);
  binarySearchTree.insert(9);

  expect(rob(binarySearchTree.getRoot())).toBe(27);
});


You can use the [editor on GitHub](https://github.com/wulei-666/wulei.github.io/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/wulei-666/wulei.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
