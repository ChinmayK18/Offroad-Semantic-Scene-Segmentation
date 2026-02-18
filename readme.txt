DUALITY AI OFFROAD SEMANTIC SCENE SEGMENTATION


Team Name
Digital Disrupters
Team Members
* Vansh Singh (25BCE10723)

* Chinmay Kumar (25BCE10865)

* Ravi Prakash Rai (25BAI11199)

* Sammireddy Varshini Reddy (25BAI11554)

Role Distribution: AI Engineering + Documentation


Project Overview
This project focuses on multi-class semantic segmentation using synthetic desert environment data generated from the Duality AI Falcon digital twin platform.
Unlike traditional image classification, semantic segmentation assigns a class label to each pixel, making it a dense prediction problem requiring spatial understanding.


Problem Statement
The objective is to train a model that classifies every pixel into one of the following classes:
   * Trees

   * Lush Bushes

   * Dry Grass

   * Dry Bushes

   * Ground Clutter

   * Flowers

   * Logs

   * Rocks

   * Landscape

   * Sky

Tech Stack & Environment
Framework: PyTorch
Environment: Anaconda (EDU environment)
GPU: NVIDIA GTX 1650 (4GB VRAM)
Training Parameters:
      * Optimizer: Adam

      * Learning Rate: 1e-4

      * Batch Size: 2

      * Loss Function: Cross Entropy Loss

A small batch size was used due to GPU memory constraints.


Training Workflow
         1. Model trained using train.py.

         2. The dataset is split into training and validation sets.

         3. Strict separation maintained between training and test data.

         4. Final evaluation conducted on unseen test images.

Evaluation Metric
Performance is evaluated using Mean Intersection over Union (Mean IoU).
IoU Formula:
IoU = TP / (TP + FP + FN)
Mean IoU measures overlap between predicted masks and ground truth masks and are suitable for segmentation tasks.
Experimental Setup
Two experimental trials were conducted to progressively improve model performance.


Trial 1 — Baseline Training
            * Epochs: 10

            * Objective: Establish baseline performance.

Final Validation Results
               * Validation Loss: 0.8154

               * Validation IoU: 0.2935

               * Validation Dice Score: 0.4381

               * Validation Pixel Accuracy: 0.7030

Test Evaluation
Mean IoU: 0.2275
Per-Class IoU:
                  * Background: 0.0000

                  * Trees: 0.0686

                  * Lush Bushes: 0.0149

                  * Dry Grass: 0.1475

                  * Dry Bushes: 0.0540

                  * Ground Clutter: 0.0527

                  * Logs: 0.0077

                  * Rocks: 0.2321

                  * Landscape: 0.5282

                  * Sky: 0.9389

Trial 2 — Final Optimized Training
                     * Objective: Final refinement and performance optimization.

Final Validation Results
                        * Validation Loss: 0.7871

                        * Validation IoU: 0.3099

                        * Validation Dice Score: 0.4569

                        * Validation Pixel Accuracy: 0.7102

Test Evaluation
Mean IoU: 0.2272
Per-Class IoU:
                           * Background: 0.0000

                           * Trees: 0.0876

                           * Lush Bushes: 0.0151

                           * Dry Grass: 0.1538

                           * Dry Bushes: 0.0604

                           * Ground Clutter: 0.0515

                           * Logs: 0.0117

                           * Rocks: 0.2049

                           * Landscape: 0.5046

                           * Sky: 0.9531
Evaluation Metric
Mean Intersection over Union (Mean IoU):
IoU = TP / (TP + FP + FN)
Mean IoU measures overlap between predicted masks and ground truth masks and is more suitable for segmentation tasks than raw accuracy.


Result Analysis
                              * Highest performance achieved on Sky due to strong visual contrast.

                              * Landscape class achieved stable segmentation performance.

                              * Vegetation classes showed lower IoU due to visual similarity.

                              * Small-scale objects like Logs and Flowers remain challenging.

Training curves demonstrate:
                                 * Stable loss convergence.

                                 * Gradual IoU improvement.

                                 * Increasing Dice score across epochs.

                                 * Consistent pixel accuracy growth.

 Failure Case Analysis
                                    * Confusion between Dry Grass and Dry Bushes.

                                    * Logs are sometimes classified as Ground Clutter.

                                    * Small objects are harder to detect due to scale imbalance.

Challenges Faced
                                       * Limited GPU memory (4GB VRAM).

                                       * Computational complexity of dense pixel prediction.

                                       * High texture similarity among vegetation classes.

Future Improvements
                                          * Class-weighted loss for imbalance handling.

                                          * Advanced data augmentation strategies.

                                          * Learning rate scheduling.

                                          * Mixed precision training.

                                          * Domain adaptation for real-world deployment.