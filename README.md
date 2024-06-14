# DockerManager
A simple yet effective Docker Manager written in Python. Mostly to meet my needs to setup tooling to make dockerization easy and effective.


## Getting Started
1. clone the repository locally
2. create a local virtual environment
3. build a docker workflow using the DockerManager

## Example Usage

```python
if __name__ == "__main__":
    manager = DockerManager('/path/to/Dockerfile')
    image_id, logs = manager.build_image(tag='my_app_image')
    print(f'Image ID: {image_id}')
    
    # Run a Python file
    container_id = manager.run_python_file(image_id, '/path/to/script.py', ports={'22/tcp': 2222})
    print(f'Container ID (Python File): {container_id}')
    
    # Run a Flask app
    container_id = manager.run_flask_app(image_id, '/path/to/flask/app', port_mapping={'5000/tcp': 5000})
    print(f'Container ID (Flask App): {container_id}')
    
    # Run a Java app
    container_id = manager.run_java_app(image_id, '/path/to/app.jar', ports={'8080/tcp': 8080})
    print(f'Container ID (Java App): {container_id}')
    
    # Run a Spring Boot app with Gradle
    container_id = manager.run_spring_boot_app(image_id, '/path/to/spring/boot/app', port_mapping={'8080/tcp': 8080})
    print(f'Container ID (Spring Boot App with Gradle): {container_id}')
    
    # Run an Express.js app
    container_id = manager.run_express_app(image_id, '/path/to/express/app', port_mapping={'3000/tcp': 3000})
    print(f'Container ID (Express App): {container_id}')
```
