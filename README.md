## kickstarter_education_usd_0428.xlsx (Project Level  Education Data)

### Unique Project Identifiers Consistency:
We confirm that each project's unique identifier (`ProjectID`) has remained consistent in both the March and April versions of the dataset.

### Data Deduplication:
This version of the dataset has undergone deduplication based on `CreatorName`, `ProjectName`, `Verified`, and `StartDate` to remove duplicate entries.

### Education Related Feature :
**High_Educated_Bio** (Boolean): A binary indicator (True/False) signifying the presence of educational context within the biography section. True for high educated (with keywords in the biography mentioning a bachelor's degree or above). Words like 'University' are recognized regardless of how they are capitalized. For example, 'university', 'University' would all be detected similarly. 

**Education_Level** (Category): Categories of the highest education level mentioned in the creator's biography.
  - "Below Bachelors": High school or lower/not indicated. 
  - "Bachelors": Bachelor's,
  - "Graduate": Graduate, 
 - "Doctorate": Doctorate degree.
 - Please note that "Below Bachelors" encompasses situations where there are no keywords in the biography mentioning a bachelor's degree or higher education, and be aware that the name might be misleading.
#### New Variable:

The project introduces the following new features:

- **Edu_Keywords_Occurrence:** A dictionary-like object (Counter) that stores the occurrence of each educational keyword in the given context.
  
- **Edu_Unique_Keywords:** A list of unique educational keywords present in the given context in lower case.
  
- **Edu_Total_Appearance:** The total number of times educational keywords in lower case appear in the given context.
  
- **Edu_Word_Count:** The total number of words in all the educational keywords present in the given context.
- 'Middle_School_Context'
- 构造一个high school的list

#### Example 1:
- **Project ID:** 6464
- **Biography:** 
  [`Biography`  text omitted for brevity]
- **Education Context:** ['degree', 'degree', 'graduate', 'University', 'University', 'College']
- **High Educated Bio:** True
- **Education Level:** Bachelors
- **Edu Keywords Occurrence:** Counter({'degree': 2, 'university': 2, 'graduate': 1, 'college': 1})
- **Edu Unique Keywords:** ['degree', 'graduate', 'university', 'college']
- **Edu Total Appearance:** 6
- **Edu Word Count:** 6
  
#### Example 2:
- **Project ID:** 48357
- **Biography:** 
  [`Biography` text omitted for brevity]
- **Education Context:** []
- **High Educated Bio:** False
- **Education Level:** Below Bachelors
- **Edu Keywords Occurrence:** Counter()
- **Edu Unique Keywords:** []
- **Edu Total Appearance:** 0
- **Edu Word Count:** 0

### Detailed Variable Descriptions:

1. **ProjectID** (Integer): Unique identifier for each project.
   
2. **High_Educated_Bio** (Boolean): Indicates whether the creator's biography mentions a high level of education.

3. **Education_Level** (Category): Categories of the highest education level mentioned in the creator's biography.

4. **Education_Context** (List of Strings): A list of high educational context keywords extracted from the creator's biography.

5. **Edu_Unique_Keywords** (List of Strings): A list of unique educational keywords present in the given context.

6. **Edu_Total_Appearance** (Integer): The total number of times educational keywords appear in the given context.

7. **Edu_Word_Count** (Integer): The total number of words in all the educational keywords present in the given context.

8. **Edu_Keywords_Occurrence** (Counter): A dictionary-like object (Counter) that stores the occurrence of each educational keyword in the given context.
