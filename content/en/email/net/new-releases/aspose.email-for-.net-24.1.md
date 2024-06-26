---

title: "Aspose.Email .NET 24.1: Improved HTML Export Options (MSI)"
description: "C# developers can enhance email processing in .NET apps with Aspose.Email .NET 24.1. Download MSI to improve resource handling for HTML export & more."
keywords: ""
page_type: single_release_page
folder_link: "/email/net/new-releases/aspose.email-for-.net-24.1/"
folder_name: "Aspose.Email for .NET 24.1"
download_link: "/email/net/new-releases/aspose.email-for-.net-24.1/d52daecb15e92f534828f6a3e635b6f4-11-10266"
download_text: "Download"
intro_text: "It contains Aspose.Email for .NET 24.1 release"
image_link: "/resources/img/msi-icon.png"
download_count: " 31/1/2024 Downloads: 1  Views: 1 "
file_size: "File Size: 53.32MB"
parent_path: "email/net"
section_parent_path: "email/net"

tags: ""
release_notes_url: "https://releases.aspose.com/email/net/release-notes/2024/aspose-email-for-net-24-1-release-notes/"
weight: 585

---

{{< Releases/ReleasesWapper >}}
  {{< Releases/ReleasesHeading H2txt="Aspose.Email for .NET 24.1" imagelink="/resources/img/msi-icon.png">}}
  {{< Releases/ReleasesButtons >}}
    {{< Releases/ReleasesSingleButtons text="Download" link="/email/net/new-releases/aspose.email-for-.net-24.1/d52daecb15e92f534828f6a3e635b6f4-11-10266" >}}
    {{< Releases/ReleasesSingleButtons text="Support Forum" link="https://forum.aspose.com/c/email" >}}
  {{< Releases/ReleasesButtons >}}
  {{< Releases/ReleasesFileArea >}}
    {{< Releases/ReleasesHeading h4txt="File Details">}}
    {{< Releases/ReleasesDetailsUl >}}
      {{< Common/li >}} Downloads: {{< /Common/li >}}
      {{< Common/li class="downloadcount" id="dwn-update-d52daecb15e92f534828f6a3e635b6f4-11-10266" >}} 1 {{< /Common/li >}}
      {{< Common/li >}} File Size: {{< /Common/li >}}
      {{< Common/li id="size-update-d52daecb15e92f534828f6a3e635b6f4-11-10266" >}} 53.32MB {{< /Common/li >}}

      {{< Common/li >}} Date Added: {{< /Common/li >}}
      {{< Common/li id="added-update-d52daecb15e92f534828f6a3e635b6f4-11-10266" >}}31/1/2024 {{< /Common/li >}}
    {{< /Releases/ReleasesDetailsUl >}}

  {{< Releases/ReleasesFileFeatures >}}
      <h4>Release Notes</h4><div><a href='https://releases.aspose.com/email/net/release-notes/2024/aspose-email-for-net-24-1-release-notes/'>https://releases.aspose.com/email/net/release-notes/2024/aspose-email-for-net-24-1-release-notes/</a></div>
  {{< /Releases/ReleasesFileFeatures >}}
  {{< Releases/ReleasesFileFeatures >}}
      <h4>Description</h4><div class="HTMLDescription">It contains Aspose.Email for .NET 24.1 release (MSI installer).</div>
  {{< /Releases/ReleasesFileFeatures >}}

{{< Releases/ReleasesHeading h4txt="Notable Features">}}
{{< Common/wrapper class="HTMLDescription">}}
{{% Releases/ReleasesFileFeatures %}}

### Improved Resource Folder Naming for HTML Export

Aspose.Email for .NET 24.1 introduces better compatibility when saving email messages as HTML with embedded resources. We have improved the naming convention of the resource folders. For instance, in the following C# coding example, if you save the HTML file as 'target.html', the associated (default) resource directory name will be 'target_files'.

```C#
var msg = MapiMessage.Load(sourceFileName);

var htmlSaveOptions = new HtmlSaveOptions
{
    ResourceRenderingMode = ResourceRenderingMode.SaveToFile,
    UseRelativePathToResources = true
};

msg.Save(Path.Combine("target.html"), htmlSaveOptions);

```
*[Source\*](https://releases.aspose.com/email/net/release-notes/2024/aspose-email-for-net-24-1-release-notes/)*

### Bug Fixes

This update to the C# email processing API includes important bug fixes related to relative recurrence parsing, UTF-7 encoding, attachment name and extension, and MSG to MHTML rendering.


> You can view the list of all new features, enhancements, and bug fixes introduced in this release by visiting [Aspose.Email for .NET 24.1 Release Notes](https://releases.aspose.com/email/net/release-notes/2024/aspose-email-for-net-24-1-release-notes/).


{{% /Releases/ReleasesFileFeatures %}}

{{< /Common/wrapper >}}
{{< /Releases/ReleasesFileFeatures >}}

 {{< /Releases/ReleasesFileArea >}}
{{< /Releases/ReleasesWapper >}}


