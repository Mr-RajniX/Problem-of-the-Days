## Problem of the Day - [<a href="https://leetcode.com/problems/implement-trie-prefix-tree/description/"> 208. Implement Trie (Prefix Tree) </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    class TrieNode {
public:
    bool isWord;
    TrieNode* children[26];
    
    TrieNode() {
        isWord = false;
        memset(children, 0, sizeof(children)); // Initialize all children to null
    }
};

class Trie {
private:
    TrieNode* root;
    
public:
    Trie() {
        root = new TrieNode();
    }
    
    void insert(string word) {
        TrieNode* node = root;
        for (char c : word) {
            int index = c - 'a';
            if (!node->children[index]) {
                node->children[index] = new TrieNode();
            }
            node = node->children[index];
        }
        node->isWord = true;
    }
    
    bool search(string word) {
        TrieNode* node = root;
        for (char c : word) {
            int index = c - 'a';
            if (!node->children[index]) {
                return false;
            }
            node = node->children[index];
        }
        return node->isWord;
    }
    
    bool startsWith(string prefix) {
        TrieNode* node = root;
        for (char c : prefix) {
            int index = c - 'a';
            if (!node->children[index]) {
                return false;
            }
            node = node->children[index];
        }
        return true;
    }
};


</pre>
