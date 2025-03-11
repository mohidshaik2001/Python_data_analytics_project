
# THE ANALYSIS

## 1.What are the most demanded skills for top 3 data roles?

to find the most demanded skills  for top 3 most popular roles .I filtered all roles with maximum postings and then filtered skills for each role with top 5 count.

view my notebook 

[skill demand of top 3 data roles](./3_Project/2_Skills_Demand.ipynb)

### visualisation

    fig,ax=plt.subplots(3,1)
    for i,job_title in enumerate(job_titles):
        df_plot= df_skills_percentage[df_skills_percentage['job_title_short']==job_title].head(5)
        sns.barplot(y='job_skills',x='percentage',ax=ax[i],hue="percentage",data=df_plot,palette='dark:b_r')
        ax[i].set_title(f'{job_title} Top 5 Skills')
    
        ax[i].set_ylabel('')
        ax[i].set_xlabel('')
        ax[i].legend().set_visible(False)
        ax[i].set_xlim(0,72)
        for n,v in enumerate(df_plot['percentage']):
            ax[i].text(v+1,n,f'{v:.0f}%',va='center')
        if i!=len(job_titles)-1:
            ax[i].set_xticks([])    
    plt.suptitle('Percentage of top 5 skills in Job Postings')
    plt.tight_layout()
    plt.show()



### result

![Visualization](./3_Project/images/skill_demand_roles.png)

### Insights

### **Role-Specific Insights**
- **Data Analyst**: SQL (47%) and Excel (34%) dominate, with growing Python (29%) adoption for advanced analysis.
- **Data Engineer**: SQL (61%) and Python (58%) are core, with AWS (33%) and Spark (29%) essential for cloud and big data.
- **Data Scientist**: Python (66%) and SQL (46%) lead, with R (17%) and Tableau (17%) for statistical analysis and visualization.

### **Overall Insights**
1. **SQL and Python Universality**: SQL and Python are foundational across all roles, emphasizing their importance in data querying, analysis, and automation.
2. **Tool Specialization**: While Data Analysts focus on visualization (Tableau, Power BI), Data Engineers prioritize cloud (AWS, Azure) and big data (Spark), and Data Scientists lean towards statistical tools (R, SAS).