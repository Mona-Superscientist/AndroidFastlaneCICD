# Android App Deployment with Fastlane + GitHub Actions CI / CD

A sample repository to demonstrate the Automate publishing app to the _Google Play Store_ with GitHub Actions⚡+ Fastlane🏃.  

### [_**Refer this article for information**_](#)
> This article includes all steps or related information for setting up this.

## Status

| Deployment Status (Production)                                                                                             | Deployment Status (Beta)                                                                                       |
|----------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| ![Release (Production)](https://github.com/PatilShreyas/AppDeployFastlaneCICD/workflows/Release%20(Production)/badge.svg)  | ![Release (Beta)](https://github.com/PatilShreyas/AppDeployFastlaneCICD/workflows/Release%20(Beta)/badge.svg)  |

---

## Workflows

- [`releaseBeta.yml`](.github/workflows/releaseBeta.yml) - For deploying application (AAB) to the _beta_ track on to the Google Play Store.
- [`releaseProd.yml`](.github/workflows/releaseProd.yml) - For deploying application (AAB) to the _production_ track on to the Google Play Store.

## Fastlane config

#### - Fastfile

```ruby
    desc "Deploy a beta version to the Google Play"
    lane :beta do
        gradle(task: "clean bundleRelease")
        upload_to_play_store(track: 'beta', release_status: 'draft')
    end

    desc "Deploy a new version to the Google Play"
    lane :production do
        gradle(task: "clean bundleRelease")
        upload_to_play_store(release_status: 'draft')
    end
```

## References

- [Fastlane](https://fastlane.tools/)
- [GitHub Actions CI/CD](https://github.com/features/actions)
