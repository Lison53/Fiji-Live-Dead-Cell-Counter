## Fiji-Live-Dead-Cell-Counter

A Fiji/ImageJ macro for automated live/dead cell counting in microscopy images stored in CZI format

# Features

    Imports CZI images using Bio-Formats.
    Processes individual image series.
    Splits multichannel images into separate channels.
    Detects intensity maxima using configurable prominence thresholds.
    Calculates estimated living-cell and dead-cell counts, total counts, and percentage of dead cells.
    Exports results to CSV.

# Configuration

The following parameters can be adjusted in the macro:

    maxSeries: maximum number of series indices to test.
    promC1: prominence threshold for the living-cell channel.
    promC3: prominence threshold for the dead-cell channel.
    livingChannelIndex: index of the living-cell channel after channel splitting.
    deadChannelIndex: index of the dead-cell channel after channel splitting.

# Output

The macro generates a CSV table containing:

    Series
    Dead cells
    Living cells
    Total
    % dead cells

The percentage of dead cells is calculated as:

100 × dead cells / total cells

# Method and limitations

Cell counts are estimated using the ImageJ Find Maxima command. This method detects intensity maxima and does not independently identify or segment cells.

The accuracy of the estimates depends on image quality, cell density, background intensity, acquisition settings and detection thresholds.

The macro should be validated against manual counts or an independently validated method before being used for quantitative biological conclusions.

The current implementation assumes that the living and dead channels can be identified by their positions in the list of split-channel image windows. It also uses a configurable maximum series index rather than automatically determining the number of available series.
