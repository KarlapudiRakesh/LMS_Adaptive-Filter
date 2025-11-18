# Adaptive Noise Cancellation using LMS Algorithm

## Objective
Implement an adaptive filter using the Least Mean Squares (LMS) algorithm to remove noise from a corrupted sine wave and estimate the original clean signal.

## Methodology

### 1. Generate the Signals
• A clean 50 Hz sine wave is generated as the primary desired signal.  
• Random Gaussian noise is added to create the corrupted signal.  
• This noisy signal is fed into the adaptive LMS filter.

### 2. Implement the LMS Algorithm
The LMS algorithm adaptively adjusts filter weights to recover the clean signal.

Core steps:
• Maintain a tap-delay buffer for input samples.  
• Compute the filter output using the current weights.  
• Calculate the error between the true clean signal and the estimated output.  
• Update the weights using the LMS rule:

w(n+1) = w(n) + μ * e(n) * x(n)

Where:  
• μ = learning rate  
• e(n) = instantaneous error  
• x(n) = input vector  

Over time, the filter learns the pattern of the clean sine wave and suppresses noise.

### 3. Train the Adaptive Filter
• The filter iteratively updates its weights to minimize the error.  
• The LMS output gradually converges toward the clean sine wave.  
• Noise components are reduced as the algorithm converges.  
• The error signal decreases across iterations, demonstrating effective noise cancellation.

## Analysis
• The algorithm is applied to a noisy 50 Hz sine wave.  
• LMS attempts to reconstruct the clean waveform from the corrupted input.  
• Performance is evaluated using MAE (Mean Absolute Error) and MSE (Mean Squared Error).  
• Comparison of original, noisy, and filtered signals shows clear improvement.

## Expected Outcomes
• Corrupted Signal: Shows the noisy sine wave.  
• LMS Filtered Output: Closely matches the original clean waveform.  
• Error Signal: Shows decreasing error over time.  
• Metrics (MAE & MSE): Quantify the accuracy of noise reduction.
