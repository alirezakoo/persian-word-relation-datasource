# persian-word-relation-datasource
- a comprehensive and structured knowledge base of the apparent and semantic relationship of all Persian words
- more than 50,000 persian words
- more than 86,000 relationship between words
- compute similarity string between words with multiple algorithms

## requirement: 
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

## Result:
![image](https://user-images.githubusercontent.com/8724064/155153741-84e9a5da-6203-4498-a240-f069797efbf0.png)
![image](https://user-images.githubusercontent.com/8724064/155155228-a9e7a7a0-3c0c-4932-a789-0643bc44fd4d.png)
![image](https://user-images.githubusercontent.com/8724064/155155501-eb94cb51-fdc9-4c74-896d-7377e2f31e34.png)

# donate
Bitcoin (BTC):    bc1qvuufkhq2hp0exj0ntlqxtjw8u39jp88eyg2kxl
![image](https://user-images.githubusercontent.com/8724064/155159294-638e8edd-2de7-4f7b-bf32-c4051e8d769b.png)

Ethereum (ETH):   0x4F15156F555b5033e679706782f0B1e61Fc8d304
![image](https://user-images.githubusercontent.com/8724064/155159243-793cfd23-aca0-4223-9965-4848577d7085.png)


