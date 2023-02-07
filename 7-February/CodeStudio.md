## Problem of the Day - [<a href="https://www.codingninjas.com/codestudio/problems/pretty-json_1112618">Code Studio</a>]


#### ⭐<ins>Solution Codes</ins> -
<pre>
  ⭐Level : EASY - <a href="https://www.codingninjas.com/codestudio/problems/pretty-json_1112618">PRETTY JSON</a>
   auto r = 0;  
    vector<string> result(1, "");
    int brace = 1;
    for (auto i = 0; i < str.length(); ++i) {
        switch (str[i]) {
            case ' ':
                continue;
            case '{':
            case '[':
                if (brace == 1 && r == 0)  
                    result[r] += str[i];
                else {
                    result.push_back("");
                    result[++r] += string(brace, '\t');
                    result[r] += str[i];
                    ++brace;
                }
                result.push_back("");
                result[++r] += string(brace, '\t');
                break;

            case '}':
            case ']':
                if (brace > 1) {
                    result.push_back("");
                    result[++r] += string(brace - 1, '\t');
                    result[r] += str[i];
                    --brace;
                } else {
                    result.push_back("");
                    result[++r] += str[i];
                    --brace;
                }
                break;

            case ',':
                result[r] += str[i];
                // Corner case check.
                if (str[i + 1] == '{' || str[i + 1] == '[')
                    continue;
                else {
                    result.push_back("");
                    result[++r] += string(brace, '\t');
                }
                break;

            case ':':
                result[r] += str[i];
                if (str[i + 1] == '{' || str[i + 1] == '[') {
                    result.push_back("");
                    result[++r] += string(brace, '\t');
                    result[r] += str[++i];
                    ++brace;
                    if (str[i + 1] != '{' && str[i + 1] != '[') {
                        result.push_back("");
                        result[++r] += string(brace, '\t');
                        result[r] += str[++i];
                    }
                }
                break;

            default:
                result[r] += str[i];
                break;
        }
    }
    return result;
</pre>
