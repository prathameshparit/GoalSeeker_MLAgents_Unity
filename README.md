## GoalSeeker

### Overview
GoalSeeker is a Unity ML-Agents project that demonstrates a reinforcement learning agent trained to navigate towards a target while avoiding obstacles. The agent learns to optimize its movement in a 3D environment by receiving rewards for reaching the goal and penalties for hitting walls. The project showcases fundamental reinforcement learning principles using Unity's ML-Agents Toolkit.

### Features
- **Reinforcement Learning Agent:** Uses the Proximal Policy Optimization (PPO) algorithm for training.
- **Dynamic Environment:** The target's position is randomized at the start of each episode, providing diverse training scenarios.
- **Rewards and Penalties:** The agent is rewarded for reaching the goal and penalized for collisions with walls.
- **Training Visualizations:** Includes a demo video, images of the training process in the command line, TensorBoard metrics, and the Unity environment.

### Demo
- A video showcasing the trained agent's behavior.
  <video src="https://github.com/user-attachments/assets/41a070d4-94a1-48d6-9d00-b19045e84ba0" controls="controls" style="max-width: 100%;">
    Your browser does not support the video tag.
  </video>
  
- **Images:**
  - Screenshot of the Unity environment during a demo run.
    ![Screenshot 2024-10-22 213819](https://github.com/user-attachments/assets/7eb863f8-6339-4be5-b397-34ae5445923c)
  - Command line output showing the training process.
    ![Screenshot 2024-10-22 211025](https://github.com/user-attachments/assets/e5b0c3c7-e131-40c7-a7ce-5546ac54ad25)
  - TensorBoard metrics visualizing the training progress.
    ![Screenshot 2024-10-22 211340](https://github.com/user-attachments/assets/26c08d79-efe6-4408-8bc5-dd9cbd34fc67)

### Installation and Setup
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/GoalSeeker.git
   ```
2. **Setup Unity ML-Agents:**
   - Follow the instructions to install Unity ML-Agents Toolkit [here](https://github.com/Unity-Technologies/ml-agents).
   - Ensure you have Python installed along with the required dependencies.

3. **Open the Project in Unity:**
   - Open the `GoalSeeker` Unity project.
   - Ensure the ML-Agents package is properly installed in Unity.

4. **Training the Agent:**
   - Run the following command in the command line to start training:
     ```bash
     mlagents-learn config/goal_seeker_config.yaml --run-id=GoalSeekerRun1
     ```
   - Press the Play button in the Unity Editor to begin training.

5. **Monitoring Training Progress:**
   - Use TensorBoard to visualize the training metrics:
     ```bash
     tensorboard --logdir=results/GoalSeekerRun1
     ```
   - Open a web browser and navigate to `http://localhost:6006` to view TensorBoard.

### How It Works
- The agent starts at a fixed position while the goal is placed randomly within a designated area.
- The agent learns to navigate towards the goal by using continuous action spaces (move along X and Z axes).
- Rewards are provided for reaching the target, and penalties are applied for colliding with walls.
- Training continues until the agent consistently reaches the goal without collisions.




### Configuration
The training configuration file (`goal_seeker_config.yaml`) contains hyperparameters for the PPO algorithm, including:
- `batch_size`: Number of training samples used in each training update.
- `buffer_size`: Number of samples collected before updating the model.
- `learning_rate`: Step size for gradient descent updates.
