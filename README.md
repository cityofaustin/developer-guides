# Developer Guides

[http://developer-guides.austintexas.io](http://developer-guides.austintexas.io)

---

:construction: This is a work in progress

This repo contains extensive documentation around workflows, best practices, tools, and architectural considerations for web developers at the City of Austin.

The site uses the [Zilker Jekyll theme](https://github.com/cityofaustin/zilker-theme) for UI and navigation handling. Future changes might be required to frontmatter and `_config.yml` based on future iterations. Zilker is currently undergoing structural changes to nav, layouts, and CSS.

Learn more about Jekyll at [the Jekyll documentation site](https://jekyllrb.com/docs/home/)

## Quick Start

1. Clone the repo  

   ```
   $ git clone https://github.com/cityofaustin/developer-guides
   ```

2. `cd` into the project directory and install gems  

   ```
   $ bundle install
   ```



3. Run the jekyll server to view the site locally  

   ```
   $ jekyll serve
   ```

4. View your site locally at [http://localhost:4000](http://localhost:4000)


## Maintainers

- Amenity Applewhite ([@amenity](https://github.com/amenity))
- Matt Langan ([@mattlangan](https://github.com/mattlangan))

## Contributing

Follow the Application Development Workflow prescribed in these guides. Once you've opened a Pull Request you can assign it to one of the project maintainers for review.

Other notes:

- You may notice that the `_site/` directory changes do not show up when you do a `$ git status`. That's because it would cause too many conflicts with multiple editors. Instead, just commit your markdown-based content changes and let the build process and CI handle the generation of `_site/`.

- If linking to other pages within the site use a relative URL structure, keeping in mind how Jekyll will compile directories and sub-directories.  
  Good: `[my link text](../dir_path/file_name)`  

  Bad: `[my link text]({% site.baseurl %}/dir_path/file_name.md)`

## Environments

### Production

- **URL:** [http://developer-guides.austintexas.io](http://developer-guides.austintexas.io) 

- **GitHub:** `master`

- **Deployment:**

  - `master` can only be updated via a pull request, and a pull request can only be merged if it passes status checks from Travis.

  - The site is set up for continuous integration via Travis CI. When a PR is opened, Travis builds the site to make sure there are no compiling or config errors. When `master` is updated via a merge it builds _and_ deploys the resulting `_site/` directory to the AWS S3 bucket.

  - As it stands, Travis does will not remove deleted files from the S3 bucket upon deploy, however there is [an open Issue on GitHub](https://github.com/travis-ci/dpl/issues/661) for precisely that functionality. For now, if it's critical that files from `_site/` are deleted, the entire bucket contents can be deleted via the AWS console and then re-generated upon the next deploy, which can be done manually via the Travis GUI or via a new merged PR.

  - There are several important configurations applied to the S3 bucket:

    - A _Bucket Policy_ (In the _Permissions_ settings) that makes all the contents publicly readable  

      ```
      {
          "Version": "2008-10-17",
          "Statement": [
              {
                  "Sid": "AllowPublicRead",
                  "Effect": "Allow",
                  "Principal": {
                      "AWS": "*"
                  },
                  "Action": "s3:GetObject",
                  "Resource": "arn:aws:s3:::coa-developer-guides/*"
              }
          ]
      }
      ```

    - Enabled _Static website hosting_ (in the _Properties_ settings), with the _Index document_ setting set as `index.html` so that requests to the root path will resolve there (rather than requiring `/index.html` added to the path)


### Local

- **URL:** [http://localhost:4000/]() 
- **Description:**
  - Run `$ jekyll serve` to start your local server
  - Run `$ jekyll build` to manually trigger a re-build of the `_site/` directory (though the site should rebuild itself whenever you make changes to the markdown files)
  - If your Jekyll server is running then changes to the markdown files will automatically trigger re-generation of the resulting html pages.
  - If you make changes to `_config.yml` then you'll need to restart your Jekyll server for them to take effect. Stop your server with `CTRL + C` and then re-run `$ jekyll serve`.
