[kbld](https://carvel.dev/kbld/)  is a Carvel tool that enables you to ensure that you're using the correct versions of software when you are creating a package. It allows you to build your package configuration with immutable image references. kbld scans a package configuration for image references and resolves those references to digests. For example, it allows you to  specify image `cert-manager:1.5.3` which is actually `quay.io/jetstack/cert-manager-controller@sha256:7b039d469ed739a652f3bb8a1ddc122942b66cceeb85bac315449724ee64287f`.

kbld scans a package configuration for any references to images and creates a mapping of image tags to a URL with a `sha256` digest. As images with the same name and tag on different registries are not necessarily the same images, by referring to an image with a digest, you're guaranteed to get the image that you're expecting. This is similar to providing a checksum file alongside an executable on a download site.