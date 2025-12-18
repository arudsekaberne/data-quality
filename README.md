# data-quality

## 🚀 Overview
The `data-quality` project is designed to ensure the integrity and reliability of data across various databases and APIs. It leverages Great Expectations for data validation and provides comprehensive logging and alerting mechanisms to notify stakeholders of any issues. This project is ideal for data engineers, and anyone responsible for maintaining data quality.

## ✨ Features
- **Database Support**: Supports MySQL and PostgreSQL databases.
- **Data Validation**: Validate data against predefined expectations.
- **Alerting**: Sends email and Teams notifications for job status updates.
- **Extensible**: Easily extendable with custom validation rules and configurations.

## 🛠️ Tech Stack
- **Programming Language**: Python
- **Frameworks & Libraries**:
  - Jinja2
  - Pandas
  - Requests
  - SQLAlchemy
  - Great Expectations

## 📦 Installation

### Prerequisites
- Python 3.8+
- MySQL or PostgreSQL

### Quick Start
```bash
# Clone the repository
git clone https://github.com/yourusername/data-quality.git

# Navigate to the project directory and set up environment variables
cd data-quality
```

## 📁 Project Structure
```
data-quality/
├── .env
├── main.py
├── dependencies/
│   ├── __init__.py
│   ├── assets/
│   │   ├── job_status_email_template.html
│   │   └── job_status_teams_template.json
│   ├── entities/
│   │   ├── __init__.py
│   │   ├── classes/
│   │   │   ├── databases/
│   │   │   │   ├── __init__.py
│   │   │   │   ├── mysql.py
│   │   │   │   └── postgre.py
│   │   │   ├── expectations/
│   │   │   │   ├── __init__.py
│   │   │   │   ├── df_expectation.py
│   │   │   │   └── sql_expectation.py
│   │   │   ├── requests/
│   │   │   │   ├── __init__.py
│   │   │   │   ├── basic_auth.py
│   │   │   │   ├── bearer_client_auth.py
│   │   │   │   └── bearer_token_auth.py
│   │   │   ├── factories/
│   │   │   │   ├── __init__.py
│   │   │   │   ├── f_database.py
│   │   │   │   ├── f_diagnose.py
│   │   │   │   └── f_request.py
│   │   │   ├── interfaces/
│   │   │   │   ├── __init__.py
│   │   │   │   ├── i_database.py
│   │   │   │   ├── i_diagnose.py
│   │   │   │   ├── i_expectation.py
│   │   │   │   └── i_request.py
│   │   │   ├── models/
│   │   │   │   ├── __init__.py
│   │   │   │   ├── config_core_model.py
│   │   │   │   ├── config_prm_model.py
│   │   │   │   ├── config_sub_model.py
│   │   │   │   ├── log_model.py
│   │   │   │   ├── process_enum.py
│   │   │   │   └── result_model.py
│   │   │   └── standard_schema.py
│   ├── functions/
│   │   ├── __init__.py
│   │   ├── checks/
│   │   │   ├── __init__.py
│   │   │   ├── check_columns.py
│   │   │   ├── check_duplicate.py
│   │   │   ├── check_nulls.py
│   │   │   ├── check_threshold.py
│   │   │   └── check_values.py
│   │   ├── core/
│   │   │   ├── __init__.py
│   │   │   ├── config_reader.py
│   │   │   ├── config_validator.py
│   │   │   ├── helper_alert.py
│   │   │   ├── helper_job.py
│   │   │   ├── helper_task.py
│   │   │   ├── helper_vault.py
│   │   │   ├── log_auditor_job.py
│   │   │   └── log_auditor_task.py
│   │   ├── matches/
│   │   │   ├── __init__.py
│   │   │   ├── match_aggregation.py
│   │   │   ├── match_count_api_table.py
│   │   │   ├── match_count_tables.py
│   │   │   └── match_row.py
│   │   └── utilities/
│   │       ├── __init__.py
│   │       ├── alert_util.py
│   │       ├── const_util.py
│   │       ├── cred_util.py
│   │       ├── df_util.py
│   │       ├── dt_util.py
│   │       ├── env_util.py
│   │       ├── js_util.py
│   │       └── log_util.py
├── tests/
│   ├── __init__.py
│   └── test_main.py
└── README.md
```

## 🔧 Configuration
- **Environment Variables**: Configure environment variables in the `.env` file.
- **Customization Options**: Extend the `dependencies/functions/checks` directory to add custom validation rules.
- **Configuration Files**: Use the `dependencies/entities/models/config_core_model.py` and `dependencies/entities/models/config_sub_model.py` files to validate job and task configurations.
