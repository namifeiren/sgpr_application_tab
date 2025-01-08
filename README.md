# Intro

The `sgpr_application_tab.csv` contains 2,846 public SG PR application records contributed by users from sgpass.info, sgprapp.com, and xiaohongshu.com. 
Now, let's make it open source for everyone! 
Wishing everyone a successful journey in Singapore!

## Table Design

```
CREATE TABLE sgpr_application_tab (
    id SERIAL PRIMARY KEY, -- removed
    author_email VARCHAR(255),
    record_nickname VARCHAR(255),

    age INT,
    gender INT, -- 0: male, 1: femal
    education INT, -- 0: High School, 1: Diploma, 2: Bachelor Degree, 3: Master Degree, 4:  Doctorate Degree, 5: Others
    education_region INT, -- 0: Singapore, 1: China, 2: Taiwan, 3: Hong Kong, 4: Macau, 5: Malaysia, 6: Indonesia, 7: India, 8: Others
    month_salary INT, -- month salary, in SGD
    region INT,  -- 0: Singapore, 1: China, 2: Taiwan, 3: Hong Kong, 4: Macau, 5: Malaysia, 6: Indonesia, 7: India, 8: Others
    race INT,   -- 0 : Chinese, 1: Malay, 2: Indian, 3: Others
    
    maritial_status INT, -- 0: Single, 1: Married, 2: Common Law, 3: Divorced, 4: separated, 5: Widowed
    applicants_number INT, -- number of applicants
    has_appeal BOOLEAN, -- has appeal or not

    is_family_apply BOOLEAN, -- is family apply or not
    has_children BOOLEAN, --  has children or not
    education_type INT, -- 0: private, 1: public, 2: 985211
    industry_sector INT, -- 0: Accommodation, 1: Admin & support services, 2: Air & sea transport, 3: Arts, entertainment & recreation, 
                        -- 4: Banking and other financial services, 5: Construction, 6: Education, 7: Food & beverage services, 
                        -- 8: Fund management services, 9: Health & social services, 10: Info-communication technology, 
                        -- 11: Insurance services, 12: Land transport & logistics, 13: Manufacturing, 14: Media, 
                        -- 15: Professional services, 16: Public admin & defence, 17: Real estate services, 18: Retail trade, 
                        -- 19: Utilities and other goods producing industries, 20: Wholesale trade, 21: Other community, social & personal services

    occupation VARCHAR(255), -- occupation
    visa_type INT, -- 0: EP, 1: S-Pass, 2: PEP, 3: LTVP, 4: STP, 5: Self-employed pass, 6: DP, 7: Others
    sg_working_months INT, -- working months in Singapore
    tax_times INT, -- tax times

    application_times INT, -- application times
    application_start_date VARCHAR(255), -- for example 2024-01-01
    application_end_date VARCHAR(255), -- for example 2024-01-01
    additional_detail TEXT,  -- for example, the reason for appeal, the salary increase, the maritial status change, the visa type change, etc.
    result INT, -- 0: Pending, 1: Approved, 2: Rejected

    c_time BIGINT, -- record create time
    m_time BIGINT, -- record modify time
    uuid UUID UNIQUE NOT NULL
    
    source INT, -- null: sgpass; 1: sgprapp; 2: xhs
);
```
