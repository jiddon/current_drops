# To run
'''
$ python3 live_slider.py
'''

# What does it do?
- If a module goes from configured to unconfigured it loses 300mA in its analogue current consumption
- Each module has 16 FEs
  - So losing one FE should show an analogue current drop of 18.75mA
- The plot produced attempts to recreate Chris's current drop size histograms with four gaussians (found in 'sim_lib.py/generate_samples')
  a) One gaussian describes the small current jumps - with a mean of 5mA and stdev of 3mA
  b) One gaussian describes the current drops if one FE loses configuration - mean 18.75mA and stdev of 3mA
  c) One gaussian is for two FE losses - mean 2 $\times$ 18.75mA and stdev 3mA
  d) One gaussian is for three FE losses - mean 3 $\times$ 18.75mA and stdev 3mA
- Each of the gaussians contribute to the plot with some proportion. The defaults are:
  a) 40%, b) 30%, c) 10%, d) 10% and another 10% for noise.
- The plot produced allows for adjustments in the proportion of each contribution, although you need to make sure the percentages add up to 100 yourself.
- Running:
  '''
  $ python3 sim_lib.py
  '''
  produces a static plot based on the settings in 'sim_lib.py/generate_samples'.
