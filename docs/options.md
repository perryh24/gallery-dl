# Command-Line Options

<!-- auto-generated by scripts/options.py -->


## General Options:
    -h, --help                  Print this help message and exit
    --version                   Print program version and exit
    -i, --input-file FILE       Download URLs found in FILE ('-' for stdin).
                                More than one --input-file can be specified
    -f, --filename FORMAT       Filename format string for downloaded files
                                ('/O' for "original" filenames)
    -d, --destination PATH      Target location for file downloads
    -D, --directory PATH        Exact location for file downloads
    -X, --extractors PATH       Load external extractors from PATH
    --proxy URL                 Use the specified proxy
    --source-address IP         Client-side IP address to bind to
    --user-agent UA             User-Agent request header
    --clear-cache MODULE        Delete cached login sessions, cookies, etc. for
                                MODULE (ALL to delete everything)
    --cookies FILE              File to load additional cookies from
    --cookies-from-browser BROWSER[+KEYRING][:PROFILE][::CONTAINER]
                                Name of the browser to load cookies from, with
                                optional keyring name prefixed with '+', profile
                                prefixed with ':', and container prefixed with
                                '::' ('none' for no container)

## Output Options:
    -q, --quiet                 Activate quiet mode
    -v, --verbose               Print various debugging information
    -g, --get-urls              Print URLs instead of downloading
    -G, --resolve-urls          Print URLs instead of downloading; resolve
                                intermediary URLs
    -j, --dump-json             Print JSON information
    -s, --simulate              Simulate data extraction; do not download
                                anything
    -E, --extractor-info        Print extractor defaults and settings
    -K, --list-keywords         Print a list of available keywords and example
                                values for the given URLs
    --list-modules              Print a list of available extractor modules
    --list-extractors           Print a list of extractor classes with
                                description, (sub)category and example URL
    --write-log FILE            Write logging output to FILE
    --write-unsupported FILE    Write URLs, which get emitted by other
                                extractors but cannot be handled, to FILE
    --write-pages               Write downloaded intermediary pages to files in
                                the current directory to debug problems

## Downloader Options:
    -r, --limit-rate RATE       Maximum download rate (e.g. 500k or 2.5M)
    -R, --retries N             Maximum number of retries for failed HTTP
                                requests or -1 for infinite retries (default: 4)
    --http-timeout SECONDS      Timeout for HTTP connections (default: 30.0)
    --sleep SECONDS             Number of seconds to wait before each download.
                                This can be either a constant value or a range
                                (e.g. 2.7 or 2.0-3.5)
    --sleep-request SECONDS     Number of seconds to wait between HTTP requests
                                during data extraction
    --sleep-extractor SECONDS   Number of seconds to wait before starting data
                                extraction for an input URL
    --filesize-min SIZE         Do not download files smaller than SIZE (e.g.
                                500k or 2.5M)
    --filesize-max SIZE         Do not download files larger than SIZE (e.g.
                                500k or 2.5M)
    --chunk-size SIZE           Size of in-memory data chunks (default: 32k)
    --no-part                   Do not use .part files
    --no-skip                   Do not skip downloads; overwrite existing files
    --no-mtime                  Do not set file modification times according to
                                Last-Modified HTTP response headers
    --no-download               Do not download any files
    --no-postprocessors         Do not run any post processors
    --no-check-certificate      Disable HTTPS certificate validation

## Configuration Options:
    -o, --option KEY=VALUE      Additional options. Example: -o browser=firefox
    -c, --config FILE           Additional configuration files
    --config-yaml FILE          Additional configuration files in YAML format
    --config-toml FILE          Additional configuration files in TOML format
    --config-create             Create a basic configuration file
    --config-ignore             Do not read default configuration files

## Authentication Options:
    -u, --username USER         Username to login with
    -p, --password PASS         Password belonging to the given username
    --netrc                     Enable .netrc authentication data

## Selection Options:
    --download-archive FILE     Record all downloaded or skipped files in FILE
                                and skip downloading any file already in it
    -A, --abort N               Stop current extractor run after N consecutive
                                file downloads were skipped
    -T, --terminate N           Stop current and parent extractor runs after N
                                consecutive file downloads were skipped
    --range RANGE               Index range(s) specifying which files to
                                download. These can be either a constant value,
                                range, or slice (e.g. '5', '8-20', or '1:24:3')
    --chapter-range RANGE       Like '--range', but applies to manga chapters
                                and other delegated URLs
    --filter EXPR               Python expression controlling which files to
                                download. Files for which the expression
                                evaluates to False are ignored. Available keys
                                are the filename-specific ones listed by '-K'.
                                Example: --filter "image_width >= 1000 and
                                rating in ('s', 'q')"
    --chapter-filter EXPR       Like '--filter', but applies to manga chapters
                                and other delegated URLs

## Post-processing Options:
    --zip                       Store downloaded files in a ZIP archive
    --ugoira-conv               Convert Pixiv Ugoira to WebM (requires FFmpeg)
    --ugoira-conv-lossless      Convert Pixiv Ugoira to WebM in VP9 lossless
                                mode
    --ugoira-conv-copy          Convert Pixiv Ugoira to MKV without re-encoding
                                any frames
    --write-metadata            Write metadata to separate JSON files
    --write-info-json           Write gallery metadata to a info.json file
    --write-tags                Write image tags to separate text files
    --mtime-from-date           Set file modification times according to 'date'
                                metadata
    --exec CMD                  Execute CMD for each downloaded file. Example:
                                --exec "convert {} {}.png && rm {}"
    --exec-after CMD            Execute CMD after all files were downloaded
                                successfully. Example: --exec-after "cd {} &&
                                convert * ../doc.pdf"
    -P, --postprocessor NAME    Activate the specified post processor
    -O, --postprocessor-option OPT
                                Additional '<key>=<value>' post processor
                                options
