<img src="../images/Airflow_logo.png" width="100" height="100" alt="Docker">


# Airflow

### ⁉️ Overview

Airflow is an open-source platform used for orchestrating complex data workflows, designed to automate, schedule, and monitor tasks in a distributed and scalable manner. Developed by Airbnb in 2014 and later contributed to the Apache Software Foundation, Airflow has become a popular tool in the data engineering community due to its flexibility, extensibility, and ease of use.

At its core, Airflow represents workflows as Directed Acyclic Graphs (DAGs), where each node is a task and the edges define the dependencies between them. Airflow's robust scheduler ensures that tasks are executed in the correct order, while its rich set of operators allows users to create custom tasks for various use cases, such as data extraction, transformation, and loading (ETL), machine learning pipelines, and data analytics.

Airflow's web-based UI makes it easy to visualize, monitor, and manage DAGs, providing insights into task execution, logs, and performance metrics. Its plugin-based architecture allows for seamless integration with a wide variety of data processing tools and platforms, ensuring that Airflow can fit into any data engineering ecosystem.

In summary, Airflow is a powerful and versatile tool for orchestrating complex data workflows, helping data engineers and organizations streamline their processes, reduce manual effort, and optimize resource utilization.

### **🧑‍🎓** Resources

Here are five excellent resources to help you learn and master Airflow:

1. Official Documentation: The Apache Airflow official documentation (**[https://airflow.apache.org/docs/](https://airflow.apache.org/docs/)**) is an invaluable resource for understanding the platform's features, concepts, and best practices. The documentation provides detailed information on getting started, configuring Airflow, creating DAGs, and using various operators, among other topics.
2. "Apache Airflow: The Hands-On Guide" by Marc Lamberti: This book provides a comprehensive and practical guide to learning Airflow. It covers the essentials of setting up Airflow, creating DAGs, and working with operators, while also delving into more advanced topics like custom operators, task communication, and scaling. The book is available for purchase on Amazon and other online bookstores.
3. "Mastering Apache Airflow" Udemy Course: Marc Lamberti, the author of the book mentioned above, also offers an online course on Udemy called "Mastering Apache Airflow" (**[https://www.udemy.com/course/mastering-apache-airflow/](https://www.udemy.com/course/mastering-apache-airflow/)**). This course covers a wide range of topics and includes hands-on exercises, quizzes, and real-world projects to help solidify your understanding of Airflow.
4. Astronomer Academy: Astronomer, a company that offers an Airflow-as-a-Service platform, provides a free learning resource called Astronomer Academy (**[https://academy.astronomer.io/](https://academy.astronomer.io/)**). This platform offers a series of tutorials and guides covering various aspects of Airflow, including installation, configuration, and working with different operators.
5. Apache Airflow GitHub Repository and Community: The official Airflow GitHub repository (**[https://github.com/apache/airflow](https://github.com/apache/airflow)**) is not only a great source of example DAGs and custom operators but also a hub for community-contributed resources. You can interact with the community through the GitHub issues, mailing lists, and Apache Airflow's Slack workspace (**[https://apache-airflow-slack.herokuapp.com/](https://apache-airflow-slack.herokuapp.com/)**) to ask questions, share your experiences, and learn from others.

By utilizing these resources, you'll be well-equipped to learn and master Apache Airflow for your data engineering needs.

### Install

Installing Apache Airflow can be done using Python's package manager, **`pip`**. Here's a step-by-step guide to installing Airflow:

1. Install Python: Airflow requires Python 3.6 or later. You can download the appropriate version for your operating system from the official Python website (**[https://www.python.org/downloads/](https://www.python.org/downloads/)**).
2. Create a virtual environment (optional, but recommended): It's a good practice to create a virtual environment for your Airflow installation to keep dependencies isolated. Use the following commands to create and activate a virtual environment:

    For Linux/macOS:

    ```bash
    python3 -m venv <your_virtual_environment_name>
    source <your_virtual_environment_name>/bin/activate
    ```

    For Windows:

    ```bash
    python -m venv <your_virtual_environment_name>
    .\<your_virtual_environment_name>\Scripts\activate
    ```

3. Install Airflow: Install Airflow using **`pip`**. It is recommended to install Airflow with the **`[constraints]`** option to avoid potential dependency conflicts. Replace **`<version>`** with the desired version of Airflow (e.g., **`2.2.3`**):

    ```bash
    pip install --upgrade pip
    pip install "apache-airflow[constraints]==<version>"
    ```

    You can also include optional extras for additional functionality, such as **`postgres`**, **`celery`**, or **`redis`**. For example, to install Airflow with PostgreSQL and Celery support, use:

    ```bash
    pip install "apache-airflow[constraints,postgres,celery]==<version>"
    ```

4. Initialize the Airflow database: By default, Airflow uses SQLite as the metadata database. To initialize the database, run:

    ```bash
    airflow db init
    ```

    If you want to use a different database, such as PostgreSQL or MySQL, you'll need to update the **`sql_alchemy_conn`** setting in the **`airflow.cfg`** file and install the necessary dependencies before running **`airflow db init`**.

5. Start the Airflow webserver: Run the following command to start the Airflow webserver:

    ```bash
    airflow webserver --port 8080
    ```

6. Start the Airflow scheduler: In a separate terminal, activate the virtual environment (if used) and run the following command to start the Airflow scheduler:

    ```bash
    airflow scheduler
    ```


Now you should have Airflow installed and running. You can access the web-based user interface by opening a browser and navigating to **`http://localhost:8080`**.

### 💻 Commands

Airflow has several command-line interface (CLI) commands that help users interact with the platform, manage workflows, and debug issues. Here are some of the most commonly used commands in Airflow:

1. **`airflow initdb`**: Initializes the Airflow metadata database. This command is typically used when setting up Airflow for the first time or after upgrading to a new version.
2. **`airflow webserver`**: Starts the Airflow webserver, which serves the web-based user interface for managing and monitoring DAGs.
3. **`airflow scheduler`**: Starts the Airflow scheduler, which is responsible for triggering tasks and managing their execution based on their dependencies and schedule.
4. **`airflow dags list`**: Lists all the available DAGs in the Airflow environment.
5. **`airflow tasks list <dag_id>`**: Lists all the tasks within a specific DAG, identified by its **`dag_id`**.
6. **`airflow dags trigger <dag_id>`**: Manually triggers a DAG run for the specified **`dag_id`**.
7. **`airflow tasks test <dag_id> <task_id> <execution_date>`**: Executes a specific task (**`task_id`**) within a DAG (**`dag_id`**) for a given execution date. This command is particularly useful for testing and debugging tasks without altering the metadata database.
8. **`airflow tasks clear <dag_id> -t <task_id> -s <start_date> -e <end_date>`**: Clears the task instance's state and logs for the specified **`task_id`** within a DAG (**`dag_id`**) between the given start and end dates. This command is useful when you want to re-run a task or a set of tasks.
9. **`airflow dags pause <dag_id>`**: Pauses the execution of a specific DAG (**`dag_id`**), preventing any new runs from being scheduled.
10. **`airflow dags unpause <dag_id>`**: Resumes the execution of a paused DAG (**`dag_id`**), allowing new runs to be scheduled.

These commands are just a subset of the many available in Airflow. For a complete list and detailed explanations, refer to the official CLI documentation: **[https://airflow.apache.org/docs/apache-airflow/stable/cli-and-env-variables-ref.html](https://airflow.apache.org/docs/apache-airflow/stable/cli-and-env-variables-ref.html)**


## Creating a DAG

_For reference, check out [Airflow's docs](https://airflow.apache.org/docs/apache-airflow/stable/concepts/dags.html)._

A DAG is created as a Python script which imports a series of libraries from Airflow.

There are [3 different ways of declaring a DAG](https://airflow.apache.org/docs/apache-airflow/stable/concepts/dags.html#declaring-a-dag). Here's an example definition using a _[context manager](https://book.pythontips.com/en/latest/context_managers.html)_:

```python
with DAG(dag_id="my_dag_name") as dag:
    op1 = DummyOperator(task_id="task1")
    op2 = DummyOperator(task_id="task2")
    op1 >> op2
```
* When declaring a DAG we must provide at least a `dag_id` parameter. There are many additional parameters available.
* The content of the DAG is composed of _tasks_. This example contains 2 _operators_, which are predefined tasks provided by Airflow's libraries and plugins.
  * An operator only has to be declared with any parameters that it may require. There is no need to define anything inside them.
  * All operators must have at least a `task_id` parameter.
* Finally, at the end of the definition we define the _task dependencies_, which is what ties the tasks together and defines the actual structure of the DAG.
  * Task dependencies are primarily defined with the `>>` (downstream) and `<<` (upstream) control flow operators.
  * Additional functions are available for more complex control flow definitions.
* A single Python script may contain multiple DAGs.

Many operators inside a DAG may have common arguments with the same values (such as `start_date`). We can define a `default_args` dict which all tasks within the DAG will inherit:

```python
default_args = {
    'start_date': datetime(2016, 1, 1),
    'owner': 'airflow'
}

with DAG('my_dag', default_args=default_args) as dag:
    op = DummyOperator(task_id='dummy')
    print(op.owner)  # "airflow"
```

For this lesson we will focus mostly on operator tasks. Here are some examples:

```python
download_dataset_task = BashOperator(
    task_id="download_dataset_task",
    bash_command=f"curl -sS {dataset_url} > {path_to_local_home}/{dataset_file}"
)
```
* A `BashOperator` is a simple bash command which is passed on the `bash_command` parameter. In this example, we're downloading some file.

```python
  format_to_parquet_task = PythonOperator(
      task_id="format_to_parquet_task",
      python_callable=format_to_parquet,
      op_kwargs={
          "src_file": f"{path_to_local_home}/{dataset_file}",
      },
  )
```
* A `PythonOperator` calls a Python method rather than a bash command.
* In this example, the `python_callable` argument receives a function that we've defined before in the DAG file, which receives a file name as a parameter then opens that file and saves it in parquet format.
* the `op_kwargs` parameter is a dict with all necessary parameters for the function we're calling. This example contains a single argument with a file name.

A list of operators is available on [Airflow's Operators docs](https://airflow.apache.org/docs/apache-airflow/stable/concepts/operators.html). A list of GCP-specific operators [is also available](https://airflow.apache.org/docs/apache-airflow-providers-google/stable/operators/cloud/index.html).

As mentioned before, DAGs can be scheduled. We can define a schedule in the DAG definition by including the `start_date` and `schedule_interval` parameters, like this:

```python
from datetime import datetime

with DAG(
    dag_id="my_dag_name",
    schedule_interval="0 6 2 * *",
    start_date=datetime(2021, 1, 1)
  ) as dag:
    op1 = DummyOperator(task_id="task1")
    op2 = DummyOperator(task_id="task2")
    op1 >> op2
```
* The scheduler will run a job ***AFTER*** the start date, at the ***END*** of the interval
* The interval is defined as a [cron job](https://www.wikiwand.com/en/Cron) expression. You can use [crontab guru](https://www.wikiwand.com/en/Cron) to define your own.
  * In this example, `0 6 2 * *` means that the job will run at 6:00 AM on the second day of the month each month.
* The starting date is what it sounds like: defines when the jobs will start.
  * The jobs will start ***AFTER*** the start date. In this example, the starting date is January 1st, which means that the job won't run until January 2nd.


## XCOM

In Airflow, XCom (short for "cross-communication") is a mechanism that allows tasks to exchange messages or small amounts of data with each other. It is particularly useful when you need to pass information between tasks in your workflows.

To export (push) XCom data from a task, you can use the xcom_push method available in the task instance's context. Here's an example of how you can use it within a PythonOperator:

```
from airflow import DAG
from airflow.operators.python_operator import PythonOperator
import datetime

def push_function(ti, **kwargs):
    value_to_push = "Some data to be passed to another task"
    ti.xcom_push(key='my_key', value=value_to_push)

dag = DAG(
    dag_id='my_dag',
    start_date=datetime.datetime.now(),
    schedule_interval="@daily"
)

push_task = PythonOperator(
    task_id='push_task',
    python_callable=push_function,
    provide_context=True,
    dag=dag
)
```
In this example, the push_function is called by a PythonOperator and exports (pushes) data using the xcom_push method. The ti variable stands for the task instance, which is automatically passed by the provide_context=True argument.

Here, my_key is the key used to store the data, and value_to_push is the actual data being pushed. You can then use this key to retrieve the data in other tasks using the xcom_pull method.

Remember that XCom data should be small, as it is stored in Airflow's metadata database. Avoid pushing large files or data structures, as this can negatively affect your system's performance.
