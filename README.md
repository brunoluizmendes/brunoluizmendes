
# Bruno Luiz Mendes 
### _"Transforming ideas into code and data into impactful solutions."_  

<p align="center">
  <a href="https://www.python.org/" target="_blank"><img src="https://img.shields.io/static/v1?label=Python&message=Always&color=success"></a>
  <a href="https://www.linkedin.com/in/brunoluizmendes/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white"></a>
  <a href="https://github.com/blmendes" target="_blank"><img src="https://img.shields.io/github/followers/blmendes?label=Follow&style=social"></a>
  <a href="https://brunoluizmendes.medium.com" target="_blank"><img src="https://img.shields.io/badge/-Medium-black?style=flat-square&logo=medium"></a>
</p>

```
#!/usr/bin/python3
# -*- coding: utf-8 -*-

class DataEngineer:
    def __init__(self, data, indent=0):
        self.data = data
        self.indent = indent

    def __print(self, value, indent, color=''):
        return f'\033[{color}m' + '\t' * indent + str(value) + '\033[0m\n'

    def __beautiful_print(self, data, indent):
        to_str = ''
        for key, value in data.items():
            if isinstance(value, dict):
                to_str += self.__print(f'\033[1m{key.upper()}\033[0m', indent, '34')  # Blue for section headers
                to_str += self.__beautiful_print(value, indent + 1)
            elif isinstance(value, list):
                to_str += self.__print(f'{key.upper()}:', indent, '33')  # Yellow for lists
                for item in value:
                    to_str += self.__print(f'- {item}', indent + 1, '32')  # Green for items in lists
            elif isinstance(value, tuple):
                to_str += self.__print(f'{key.upper()}: {value[0]}° N, {value[1]}° W', indent, '36')  # Cyan for coordinates
            else:
                to_str += self.__print(f'{key.upper()}: {value}', indent, '37')  # White for normal text
        return to_str

    def __str__(self):
        return self.__beautiful_print(self.data, self.indent)

if __name__ == '__main__':
    data = dict(
        name='Bruno Mendes',
        role='Data Engineer',
        location=(-23.550520, -46.633308),  # São Paulo coordinates
        code=['Python', 'SQL', 'Go'],
        technologies=dict(
            backEnd=['Django', 'Flask', 'FastAPI', 'Apache Iceberg', 'Spark', 'CDC', 'Kafka', 'Kinesis', 'BigQuery', 'Pub/Sub', 'Lambda', 'EMR'],
            dataInfra=['Amazon Athena', 'Apache Kinesis', 'PostgreSQL'],
            devOps=['AWS', 'Docker', 'Serverless'],
            databases=['PostgreSQL', 'DynamoDB', 'S3', 'SQL Server', 'MongoDB', 'Neptune'],
            analytics=['Google Analytics', 'Looker', 'Metabase'],
            misc=['GraphQL', 'REST APIs', 'Unit Testing', 'CI/CD', 'Agile', 'ETL', 'Data Lakes', 'Data Warehousing', 'Airflow', 'Batch Processing']
        )
    )
    bruno_mendes = DataEngineer(data)
    print(bruno_mendes)

```
