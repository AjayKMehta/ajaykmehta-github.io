if (file.exists("~/.Rprofile")) {
  base::sys.source("~/.Rprofile", envir = environment())
}

# https://alison.rbind.io/post/2019-02-21-hugo-page-bundles/
# https://blog.rstudio.com/2021/01/18/blogdown-v1.0/
options(
  blogdown.author = "Ajay Mehta",
  blogdown.ext = ".Rmd",
  blogdown.subdir = "post",
  blogdown.new_bundle = TRUE,
  blogdown.knit.on_save = FALSE,
  blogdown.serve_site.startup = FALSE,
  # New in 1.0
  blogdown.initial_files = c("config.toml", ".Rprofile"),
  blogdown.method = "markdown",
  # New in 1.1
  blogdown.server.verbose = TRUE,
  # Protect LaTeX expressions in a pair of backticks when the post output
  # format is Markdown
  blogdown.protect.math = TRUE,
  blogdown.yaml.empty = TRUE
)
