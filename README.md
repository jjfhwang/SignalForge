# SignalForge - Your TypeScript Signal Processing Toolkit

SignalForge is a robust and versatile TypeScript library designed to empower developers with a comprehensive suite of signal processing tools. Built with performance and flexibility in mind, SignalForge allows you to manipulate, analyze, and transform signals efficiently within your TypeScript applications. From basic signal generation and filtering to advanced frequency domain analysis and custom algorithm implementation, SignalForge provides the building blocks you need to tackle a wide range of signal processing tasks.

This library is engineered to bridge the gap between complex signal processing concepts and accessible TypeScript code. Whether you're building audio processing applications, analyzing sensor data, or developing sophisticated control systems, SignalForge offers a modular and extensible architecture to suit your specific needs. The library leverages modern TypeScript features and best practices to ensure type safety, maintainability, and optimal performance. Its well-documented API and comprehensive examples make it easy to integrate into existing projects and learn the ins and outs of signal processing.

SignalForge is more than just a collection of algorithms; it's a platform for innovation. The librarys design encourages users to extend its functionality by creating custom signal processing modules and algorithms. By providing a clear and consistent interface, SignalForge enables developers to easily share and reuse their contributions, fostering a collaborative ecosystem around signal processing in TypeScript. Furthermore, rigorous testing and continuous integration ensure the library remains stable and reliable, even as it evolves with new features and improvements.

Key Features

*   **Signal Generation:** Generate common signal types such as sine waves, square waves, sawtooth waves, and white noise using customizable parameters like frequency, amplitude, and phase. This feature allows you to create realistic test signals or simulate real-world scenarios. You can instantiate a sine wave generator with `const sineWave = new SignalGenerator('sine', { frequency: 440, amplitude: 1 });`
*   **Filtering:** Implement a variety of digital filters, including low-pass, high-pass, band-pass, and band-stop filters. Design filters using techniques like Butterworth, Chebyshev, and Bessel approximations. Filter creation example: `const butterworthFilter = new ButterworthFilter(4, 1000, 'lowpass', 44100);`
*   **Fourier Transform:** Perform fast Fourier transforms (FFT) and inverse fast Fourier transforms (IFFT) to analyze signals in the frequency domain. Extract key features like spectral components and power spectral density. Use with `const fftResult = FFT(signalData);`
*   **Windowing Functions:** Apply windowing functions such as Hamming, Hanning, and Blackman windows to reduce spectral leakage during Fourier analysis. Apply by calling `const windowedSignal = applyWindow(signalData, 'hamming');`
*   **Signal Statistics:** Calculate essential signal statistics, including mean, variance, standard deviation, and root mean square (RMS) value. These functions allow you to quantify signal characteristics and identify trends. Example: `const rmsValue = calculateRMS(signalData);`
*   **Time-Domain Analysis:** Offers tools for time-domain analysis such as autocorrelation and cross-correlation. These functions can be used to detect patterns and relationships within signals. Use with `const autocorrelationResult = autocorrelate(signalData);`
*   **Modular Architecture:** The library features a modular design, making it easy to add custom signal processing algorithms and modules. This allows users to tailor SignalForge to their specific needs and contribute to the library's growth.

Technology Stack

*   **TypeScript:** The library is written entirely in TypeScript, providing static typing for enhanced code maintainability and reduced runtime errors.
*   **NumJS (Optional):** While SignalForge can work with standard JavaScript arrays, using a library like NumJS (or similar numerical library) can significantly improve performance for large-scale signal processing tasks. NumJS provides optimized array operations and mathematical functions.
*   **Jest:** Used for unit testing to ensure the reliability and correctness of the library's algorithms and functionalities.
*   **ESLint/Prettier:** Employed for code linting and formatting to maintain code quality and consistency throughout the project.

Installation

1.  **Clone the repository:**
    *git clone https://github.com/jjfhwang/SignalForge.git*
2.  **Navigate to the project directory:**
    *cd SignalForge*
3.  **Install dependencies:**
    *npm install* or *yarn install*
4.  **Build the library:**
    *npm run build* or *yarn build*

Configuration

SignalForge does not require extensive configuration. However, certain modules, such as filter design, may require tuning specific parameters like cutoff frequencies and filter orders. These parameters can be passed as options when instantiating the corresponding classes.

Environment variables are not currently used but may be introduced in future versions for features like logging or external data integration.

Usage

Import the desired modules from the `dist` directory after building the library.

Example: Generating and filtering a sine wave.

// Import necessary modules
import { SignalGenerator } from './dist/signal-generator';
import { ButterworthFilter } from './dist/butterworth-filter';

// Create a sine wave generator
const sineWaveGenerator = new SignalGenerator('sine', { frequency: 1000, amplitude: 1 });

// Generate a 1-second sine wave at 44100 Hz
const sampleRate = 44100;
const duration = 1; // seconds
const signalData = sineWaveGenerator.generate(sampleRate * duration);

// Create a low-pass Butterworth filter
const butterworthFilter = new ButterworthFilter(4, 1000, 'lowpass', sampleRate);

// Filter the signal
const filteredSignal = butterworthFilter.filter(signalData);

// 'filteredSignal' now contains the filtered sine wave data.

API documentation (auto generated with typedoc) to be added to Github pages.

Contributing

We welcome contributions to SignalForge! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Write clear and concise code with proper documentation.
4.  Add unit tests to ensure the functionality of your changes.
5.  Submit a pull request with a detailed description of your changes.
6.  Adhere to the project's coding style (ESLint/Prettier).

License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/jjfhwang/SignalForge/blob/main/LICENSE) file for details.

Acknowledgements

We would like to thank the open-source community for providing valuable resources and tools that have contributed to the development of SignalForge. We also extend our gratitude to the contributors who have helped improve the library through their contributions and feedback.