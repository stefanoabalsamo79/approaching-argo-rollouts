### Argo UI Dashboard
We can run the dashboard via `Argo Rollouts Kubectl plugin` and it provides a local UI to visualize all your `rollouts`.

Start the dashboard and then visit this [`url`](http://localhost:3100)
```bash
kubectl argo rollouts dashboard
```
![image-001](./images-and-diagrams/image-001.png)

The dashboard presents 2 views:
- List view where every rollout is displayed
- Individual view where you can drill down a specific rollout and see more details related to it

**Rollout view:**
![image-002](./images-and-diagrams/image-002.png)
