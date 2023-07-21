
  
 ```dataview
 table  rows.file.frontmatter.path as file , rows.file.frontmatter.youtubeUrl as YouTubeUrl ,  rows.file.frontmatter.rate  as rate
 from "BEFORE/Person" 
group by tags

 ```