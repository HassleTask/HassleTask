
# HassleTask

[![License](https://img.shields.io/badge/license-HassleTask%20Community-blue.svg)](LICENSE)

## What is HassleTask?

HassleTask is a **serverless, no-infrastructure background task queue system** designed for developers who want to run asynchronous tasks **without managing workers, queues, or Redis**.

Inspired by Celery, HassleTask provides a **Python-first, Celery-compatible** API that offloads task execution to cloud serverless compute, enabling you to focus on writing your application logic — not infrastructure.

In the future, we plan to add support for more programming languages to broaden HassleTask’s usability.

---

## Key Features

- **Serverless & cloud-powered:** No need to manage workers or queues.  
- **Celery-compatible:** Familiar API makes migration and adoption easy.  
- **Simple Python API:** Define tasks with decorators and trigger them asynchronously.  
- **Scalable:** Automatically scales with your workload in the cloud.  
- **Local development mode:** Test tasks locally without cloud dependencies.  
- **Open Source (Source-Available):** Free for small-scale use with fair commercial terms.

---

## Getting Started

### Installation

```bash
pip install hassletask
```

### Basic Usage

```python
from hassletask import HassleTask

queue = HassleTask()

@queue.task
def add(x, y):
    return x + y

result = add.delay(3, 5)
print(result.get())  # Should print 8
```

---

## Local Development & Testing

HassleTask supports two development modes:

1. **Local in-memory mode:** Run and test tasks locally without cloud access.  
2. **Cloud mode:** Run tasks using cloud services (AWS Lambda, SQS, DynamoDB) — requires AWS credentials.

See [LOCAL_DEV_MODE.md](./LOCAL_DEV_MODE.md) for detailed setup instructions.

---

## License

This project is licensed under the **HassleTask Community License v1.0.0** — see the [LICENSE](./LICENSE) file for details.

**Summary:** Free to use for personal projects, education, and internal use by organizations with less than $1M annual revenue or less than 10,000 tasks/month. Commercial use and SaaS hosting require a commercial license.

---

## Contribution

Contributions are welcome! Please see [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines on how to report issues, request features, and submit pull requests.

---

## Roadmap

- Implement core Python task queue with local mode  
- Add AWS integration (SQS, Lambda, DynamoDB)  
- Implement retries, error handling, and monitoring  
- Launch open-source version for community use  
- Explore multi-language support  
- Plan managed SaaS offering (HassleTask Cloud)  

---

## Contact

For commercial licensing inquiries or questions, please email:  
**ayan.kakkar@gmail.com**

---

Thank you for checking out HassleTask! We’re excited to build a seamless background task experience together.
