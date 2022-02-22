# persian-word-relation-datasource
a comprehensive and structured knowledge base of the apparent and semantic relationship of all Persian words
requirement: 
SQL Server 2016 and above versions

![image](https://user-images.githubusercontent.com/8724064/155145697-2f863c43-64f5-49d0-8aa1-dd5e0ecdb519.png)

RelationTypeID
1:Synonyms
2:Opposite
![image](https://user-images.githubusercontent.com/8724064/155152795-954839f6-8bc4-4a73-b16f-aaa9c8e613b8.png)

They have also been compared with several related word similarity algorithms
https://github.com/tdebatty/java-string-similarity

```sql
SELECT        
      Word.PersianWord,
      Word_1.PersianWord AS Word2,
      case 
      when WordRelation.RelationTypeID=1 then 'Synonyms'
      when WordRelation.RelationTypeID=2 then 'Opposite'
      END AS RelationType,
      WordRelation.JaroWinklerSimilarityString,
      WordRelation.JaccardSimilarityString,
      WordRelation.LongestCommonSubsequenceDistanceString,
      WordRelation.LevenshteinSimilarityString
FROM  WordRelation INNER JOIN
      Word ON WordRelation.WordID1 = Word.WordID INNER JOIN
      ord AS Word_1 ON WordRelation.WordID2 = Word_1.WordID
```

# Result:
![image](https://user-images.githubusercontent.com/8724064/155153741-84e9a5da-6203-4498-a240-f069797efbf0.png)
