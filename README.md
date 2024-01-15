UTA Data Bootcamp Module 4
==========================

Riley Taylor  
2024-Jan-15

**Setup and Related Info**

The primary notebook is saved as "PyCitySchools.ipynb" in the "PyCitySchools" directory. This is a renamed copy of the starter code notebook provided, and I filled in/added code/expressions as needed to complete the assignment. The csv's in question are saved in "PyCitySchools/Resources". Analysis is provided in the README below as well as in the Analysis portion of the python notebook. The "Images" directory was included in the starter code, but I have removed them as I didn't see how it was related to the assignment. Sources are also enumerated below, although I didn't bother to explain their use in the project beyond their title. The majority of the sources were used for general documentation/language explorations/best practices rather than code snippets. One exception - undoing formatting like the following:
```
{
    per_school_summary["Per Student Budget"] = per_school_summary["Per Student Budget"].map("${:,.2f}".format)
...
...
    try:
        school_spending_df['Per Student Budget'] = school_spending_df['Per Student Budget'].str.replace(',','')
        school_spending_df['Per Student Budget'] = school_spending_df['Per Student Budget'].str.replace('$','')
        school_spending_df['Per Student Budget'] = school_spending_df['Per Student Budget'].astype(float)
    except:
        #means that we already applied the above
        print('No formatting applied, assuming data is already properly formatted')
}

```
We had examples like it in class to replicate this behavior, but it was faster to check online than to peek through past class notes. 

There might be a few other snippets, but the spirit of citing sources is to avoid plagiarism and give credit, and it should be evident that I am (1) not plagiarizing and (2) wanting to give credit to as many sources as possible. I jusst don't have the time to annotate each one in depth. 


-----------------------------------------




# Report:




## District Analysis

From the values we calculated, we had 15 unique schools, (ID'd 0-14), with nearly 40,000 students and a total budget of $24,649428.00. Averages for Math and Reading scores, as well as Passing Rates, left a lot to be desired. At a glance, without other districts following the same curriculum to compare this to, there isn't much that can be definitively said. 

## School Analysis

When we look at our final `per_school_summary` dataframe, the data isn't organized in a very appetizing way. Data is sorted alphabetically by school name, not according to passing rates, budget information, or school demographic data. In this format, I will only say that the range of passing rates is surpisingly high (overall rates range from the low 50's to the low 90s).

## Highest-Performing Schools (by % Overall Passing)

The biggest takeaway? The top 5 highest performing schools by overall passing percentage are charter schools. Does this imply that charter schools are better than district schools? I would argue that unless I can guarantee the curriculums/exams are the same, these values are not really comparable. But I can also see the perspective that the families that can afford charter schools/prioritize educational decisions will likely encourage and afford academic success, regardless of the quality of the teaching. 


## Lowest-Performing Schools (by % Overall Passing)

They are all district schools. Again, it doesn't mean anything on its own, especially without controlling for curriculum/exams, but it is easy to generate narratives as to why this might be the case. All of these schools each have more students than the most populous of the top 5 best performing schools in the data. District schools are the "default" school, so no extra cost/decision making was needed, and be definition if people more prone to academic success are leaving these options behind for charter schools, than charter schools will reflect higher academic success accordingly. s

## Math Scores by Grade

There is little variation in scores between grades, only variation between schools. There are many narritives one can draw, but without performing statistically significant data tests/knowing more information regarding curriculum, family income, etc, it's hard to create a definitive conclusion. 

## Reading Scores by Grade

The analysis for math scores could be repeated here in its entirety. 

## Scores by School Spending

This was interesting, but not completely surprising. We actually see a negative correlation between the amount of money spent per student and the academic success of the students in those schools. Does that imply that spending more money on a school will cause their performance to suffer? That seems like an asinine conclusion. I'd wager that we are just observing that the amount of money spent per student is far less significant of a factor on academic success than one might have guessed. Instead, factors like mean_family_income might have a much larger influence. A family that is not money insecure has a stronger capacity to prioritize academic success. Whether this factor is significant requires more data, but it seems like we have to look elsewhere than school budgets to determine school quality. 

## Scores by School Size

As you might anticipate, increasing the students in a school might put more of a burden on school resources, and could affect academic success. We see that the burden is only pronounced upwards of 2000 students, and barely noticeable before then. Whether or not this is the only factor remains the be seen, but it does seem significant. But the data does show a significant drop off in overall passing rate for large schools (>2000).

## Scores by School Type

We sort of saw this earlier, but we can very easily see that charter schools and district schools have drastically different values. My analysis has not changed however - it does provide evidence that charter schools are stronger academically, but it doesn't definitively imply that charter schools provide better educational resources than district schools. That logical jump just involves far more factors upon which this data set could not provide insight. 

------------------------

# Sources


### For District Analysis Portion of Project

python - Counting unique values in a column in pandas dataframe like in Qlik? - Stack Overflow
https://stackoverflow.com/questions/45759966/counting-unique-values-in-a-column-in-pandas-dataframe-like-in-qlik

pandas.DataFrame.groupby — pandas 2.1.4 documentation
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.groupby.html

python - How to sum values across groups without summing duplicates - Stack Overflow
https://stackoverflow.com/questions/73749095/how-to-sum-values-across-groups-without-summing-duplicates

python - Groupby and sum only one column - Stack Overflow
https://stackoverflow.com/questions/38985053/groupby-and-sum-only-one-column

python - pandas - find first occurrence - Stack Overflow
https://stackoverflow.com/questions/41255215/pandas-find-first-occurrence

python - Pandas: How to sum values in a column for duplicate rows - Stack Overflow
https://stackoverflow.com/questions/51914255/pandas-how-to-sum-values-in-a-column-for-duplicate-rows

python - Pandas groupby nlargest sum - Stack Overflow
https://stackoverflow.com/questions/40390634/pandas-groupby-nlargest-sum

pandas.DataFrame.apply — pandas 2.1.4 documentation
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.apply.html

6. Expressions — Python 3.12.1 documentation
https://docs.python.org/3/reference/expressions.html#lambda

python - Drop duplicates using pandas groupby - Stack Overflow
https://stackoverflow.com/questions/37105609/drop-duplicates-using-pandas-groupby

python - Pandas dataframe get first row of each group - Stack Overflow
https://stackoverflow.com/questions/20067636/pandas-dataframe-get-first-row-of-each-group

Different ways to create Pandas Dataframe - GeeksforGeeks
https://www.geeksforgeeks.org/different-ways-to-create-pandas-dataframe/

python - Pandas: Using variables to create dataframe with one row and column names from variable names - Stack Overflow
https://stackoverflow.com/questions/44118416/pandas-using-variables-to-create-dataframe-with-one-row-and-column-names-from-v


### For School Summary Portion of the Project


python - Remove duplicates by columns A, keeping the row with the highest value in column B - Stack Overflow
https://stackoverflow.com/questions/12497402/remove-duplicates-by-columns-a-keeping-the-row-with-the-highest-value-in-column

pandas.DataFrame.count — pandas 2.1.4 documentation
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.count.html

python - How to count the number of group elements with pandas - Stack Overflow
https://stackoverflow.com/questions/38187777/how-to-count-the-number-of-group-elements-with-pandas

Are Python variables pointers? Or else, what are they? - Stack Overflow
https://stackoverflow.com/questions/13530998/are-python-variables-pointers-or-else-what-are-they

pandas.DataFrame.rename — pandas 2.1.4 documentation
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.rename.html

python - Pandas Merge - How to avoid duplicating columns - Stack Overflow
https://stackoverflow.com/questions/19125091/pandas-merge-how-to-avoid-duplicating-columns

python - What is the difference between join and merge in Pandas? - Stack Overflow
https://stackoverflow.com/questions/22676081/what-is-the-difference-between-join-and-merge-in-pandas

python - How to (re)name an empty column header in a pandas dataframe without exporting to csv - Stack Overflow
https://stackoverflow.com/questions/41096611/how-to-rename-an-empty-column-header-in-a-pandas-dataframe-without-exporting-t

python - Creating new dataframes using groupby - Stack Overflow
https://stackoverflow.com/questions/51091331/creating-new-dataframes-using-groupby

python - How to create multiple dataframes from pandas groupby object - Stack Overflow
https://stackoverflow.com/questions/35274700/how-to-create-multiple-dataframes-from-pandas-groupby-object

python - Is there a way to create a single column pandas DataFrame from list without copying the list? - Stack Overflow
https://stackoverflow.com/questions/51329934/is-there-a-way-to-create-a-single-column-pandas-dataframe-from-list-without-copy

How to Merge Two Pandas DataFrames on Index?
https://www.tutorialspoint.com/how-to-merge-two-pandas-dataframes-on-index

python - Create new column based on values from other columns / apply a function of multiple columns, row-wise in Pandas - Stack Overflow
https://stackoverflow.com/questions/26886653/create-new-column-based-on-values-from-other-columns-apply-a-function-of-multi


### For Remainer of Project:

pandas.DataFrame.sort_values — pandas 2.1.4 documentation
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.sort_values.html

Group by: split-apply-combine — pandas 2.1.4 documentation
https://pandas.pydata.org/docs/user_guide/groupby.html#transformation

python - Change column names in Pandas Dataframe from a list - Stack Overflow
https://stackoverflow.com/questions/45468630/change-column-names-in-pandas-dataframe-from-a-list

pandas.cut — pandas 2.1.4 documentation
https://pandas.pydata.org/docs/reference/api/pandas.cut.html

pandas.Series.map — pandas 2.1.4 documentation
https://pandas.pydata.org/docs/reference/api/pandas.Series.map.html

Trying to remove commas and dollars signs with Pandas in Python - Stack Overflow
https://stackoverflow.com/questions/38516481/trying-to-remove-commas-and-dollars-signs-with-pandas-in-python

Python Try Except
https://www.w3schools.com/python/python_try_except.asp

pandas.Series.groupby — pandas 2.1.4 documentation
https://pandas.pydata.org/docs/reference/api/pandas.Series.groupby.html#pandas.Series.groupby
