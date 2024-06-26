---
id: "aspose-page-for-cpp-24-4-release-notes"
slug: "aspose-page-for-cpp-24-4-release-notes"
linktitle: "Aspose.Page for C++ 24.4 Release Notes"
title: "Aspose.Page for C++ 24.4 Release Notes"
description: C++ APIs to manipulate and process PS, EPS, and XPS files. This page contains new Aspose.Page for C++ features, enhancement, and bug fixes in 2024, version 24.4.
productName: "Aspose.Page for C++"
weight: 9
type: "repository"
layout: "release"
hideChildren: false
toc: true
family_listing_page_title: "Aspose.Page for C++ 24.4 Release Notes"
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.Page for C++ 24.4.

{{% /alert %}}

## **Improvements and Changes**

Aspose.Page for C++ 24.4 is based on [Aspose.Page for .NET 24.3](https://releases.aspose.com/page/net/release-notes/2024/aspose-page-for-net-24-3-release-notes/) and ready for use with Aspose C++ products ver 24.4.

## **Public API and Backwards Incompatible Changes**
### **Added APIs**
* T:Aspose::Page::Drawing::Drawing2D::SmoothingMode
* F:Aspose::Page::Drawing::Drawing2D::SmoothingMode::Default
* F:Aspose::Page::Drawing::Drawing2D::SmoothingMode::HighSpeed
* F:Aspose::Page::Drawing::Drawing2D::SmoothingMode::HighQuality
* F:Aspose::Page::Drawing::Drawing2D::SmoothingMode::None
* F:Aspose::Page::Drawing::Drawing2D::SmoothingMode::AntiAlias
* F:Aspose::Page::Drawing::Drawing2D::SmoothingMode::Invalid
* T:Aspose::Page::Drawing::Imaging::ImageFormat
* F:Aspose::Page::Drawing::Imaging::ImageFormat::Bmp
* F:Aspose::Page::Drawing::Imaging::ImageFormat::Jpeg
* F:Aspose::Page::Drawing::Imaging::ImageFormat::Png
* F:Aspose::Page::Drawing::Imaging::ImageFormat::Gif
* F:Aspose::Page::Drawing::Imaging::ImageFormat::Tiff
* T:Aspose::Page::Drawing::Size
* M:Aspose::Page::Drawing::Size::#ctor(System::Int32,System::Int32)
* P:Aspose::Page::Drawing::Size::Height
* P:Aspose::Page::Drawing::Size::Width
* P:Aspose::Page::Drawing::Size::IsEmpty
* M:Aspose::Page::Drawing::Size::Add(System::SharedPtr&lt;Aspose::Page::Drawing::Size&gt;,System::SharedPtr&lt;Aspose::Page::Drawing::Size&gt;)
* M:Aspose::Page::Drawing::Size::Subtract(System::SharedPtr&lt;Aspose::Page::Drawing::Size&gt;,System::SharedPtr&lt;Aspose::Page::Drawing::Size&gt;)
* M:Aspose::Page::Drawing::Size::Clone
* M:Aspose::Page::Drawing::Size::Equals(System::SharedPtr&lt;System::Object&gt;)
* M:Aspose::Page::Drawing::Size::GetHashCode
* M:Aspose::Page::Drawing::Size::ToString
* F:Aspose::Page::Drawing::Size::Empty
* M:Aspose::Page::EPS::Device::ImageSaveOptions::#ctor(Aspose::Page::Drawing::Imaging::ImageFormat)
* M:Aspose::Page::EPS::Device::ImageSaveOptions::#ctor(System::SharedPtr&lt;Aspose::Page::Drawing::Size&gt;)
* M:Aspose::Page::EPS::Device::ImageSaveOptions::#ctor(System::SharedPtr&lt;Aspose::Page::Drawing::Size&gt;,Aspose::Page::Drawing::Imaging::ImageFormat)
* M:Aspose::Page::EPS::Device::ImageSaveOptions::#ctor(System::SharedPtr&lt;Aspose::Page::Drawing::Size&gt;,Aspose::Page::Drawing::Imaging::ImageFormat,System::Boolean)
* P:Aspose::Page::EPS::Device::ImageSaveOptions::Resolution
* P:Aspose::Page::EPS::Device::ImageSaveOptions::Size
* P:Aspose::Page::EPS::Device::ImageSaveOptions::ImageFormat
* M:Aspose::Page::EPS::PsDocument::SaveAsPdf(System::String, System::SharedPtr&lt;Aspose::Page::EPS::Device::PdfSaveOptions&gt;)
* M:Aspose::Page::EPS::PsDocument::SaveAsPdf(System::SharedPtr&lt;System::IO::Stream&gt;, System::SharedPtr&lt;Aspose::Page::EPS::Device::PdfSaveOptions&gt;)
* M:Aspose::Page::EPS::PsDocument::SaveAsImage(System::SharedPtr&lt;Aspose::Page::EPS::Device::ImageSaveOptions&gt;)

### **Deprecateded APIs. This members will be hidden in 24.6.**
* T:Aspose::Page::Device
* M:Aspose::Page::Document::Save(System::SharedPtr&lt;Aspose::Page::Device&gt;,Aspose::Page::SaveOptions)
* T:Aspose::Page::EPS::PdfDevice
* T:Aspose::Page::EPS::ImageDevice
* T:Aspose::Page::XPS::Presentation::Pdf::PdfDevice
* T:Aspose::Page::XPS::Presentation::Image::ImageDevice
* T:Aspose::Page::XPS::Presentation::Ps::PsDevice
* M:Aspose::Page::EPS::PsDocument::Save(System::SharedPtr&lt;Aspose::Page::Device&gt;,Aspose::Page::SaveOptions)

### **Removed APIs**
* M:Aspose::Page::Device::#ctor
* M:Aspose::Page::Device::#ctor(System::SharedPtr&lt;Aspose::Page::Device&gt;)
* P:Aspose::Page::Device::SaveOptions
* P:Aspose::Page::Device::Properties
* P:Aspose::Page::Device::Creator
* P:Aspose::Page::Device::Size
* P:Aspose::Page::Device::IsDirectRGB
* P:Aspose::Page::Device::Background
* P:Aspose::Page::Device::Opacity
* P:Aspose::Page::Device::Stroke
* P:Aspose::Page::Device::Paint
* P:Aspose::Page::Device::OpacityMask
* P:Aspose::Page::Device::Font
* P:Aspose::Page::Device::CharTM
* P:Aspose::Page::Device::TextRenderingMode
* P:Aspose::Page::Device::TextStrokeWidth
* P:Aspose::Page::Device::IsLicensed
* M:Aspose::Page::Device::ReNew
* M:Aspose::Page::Device::GetSaveOptions
* M:Aspose::Page::Device::InitProperties(System::Collections::Generic::Dictionary{System::String,System::Object})
* M:Aspose::Page::Device::GetProperty(System::String)
* M:Aspose::Page::Device::GetPropertyColor(System::String)
* M:Aspose::Page::Device::GetPropertyRectangle(System::String)
* M:Aspose::Page::Device::GetPropertyMargins(System::String)
* M:Aspose::Page::Device::GetPropertySize(System::String)
* M:Aspose::Page::Device::GetPropertyInt(System::String)
* M:Aspose::Page::Device::GetPropertyDouble(System::String)
* M:Aspose::Page::Device::IsProperty(System::String)
* M:Aspose::Page::Device::Create
* M:Aspose::Page::Device::SetTransform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::Device::GetTransform
* M:Aspose::Page::Device::Transform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::Device::Translate(System::Double,System::Double)
* M:Aspose::Page::Device::Rotate(System::Double)
* M:Aspose::Page::Device::Rotate(System::Double,System::Double,System::Double)
* M:Aspose::Page::Device::Scale(System::Double,System::Double)
* M:Aspose::Page::Device::Shear(System::Double,System::Double)
* M:Aspose::Page::Device::InitClip
* M:Aspose::Page::Device::SetClip(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::Device::Draw(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::Device::Fill(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::Device::DrawString(System::String,System::Double,System::Double)
* M:Aspose::Page::Device::DrawImage(System::Drawing::Bitmap,System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;,System::Drawing::Color)
* M:Aspose::Page::Device::StartDocument
* M:Aspose::Page::Device::EndDocument
* M:Aspose::Page::Device::Dispose
* M:Aspose::Page::Device::Reset
* M:Aspose::Page::Device::WriteComment(System::String)
* M:Aspose::Page::Device::DrawArc(System::Double,System::Double,System::Double,System::Double,System::Double,System::Double)
* M:Aspose::Page::Device::DrawLine(System::Double,System::Double,System::Double,System::Double)
* M:Aspose::Page::Device::DrawOval(System::Double,System::Double,System::Double,System::Double)
* M:Aspose::Page::Device::DrawPolyline(System::ArrayPtr&lt;System::Int32&gt;,System::ArrayPtr&lt;System::Int32&gt;,System::Int32)
* M:Aspose::Page::Device::DrawPolyline(System::ArrayPtr&lt;System::Double&gt;,System::ArrayPtr&lt;System::Double&gt;,System::Int32)
* M:Aspose::Page::Device::DrawPolygon(System::ArrayPtr&lt;System::Int32&gt;,System::ArrayPtr&lt;System::Int32&gt;,System::Int32)
* M:Aspose::Page::Device::DrawPolygon(System::ArrayPtr&lt;System::Double&gt;,System::ArrayPtr&lt;System::Double&gt;,System::Int32)
* M:Aspose::Page::Device::DrawRect(System::Double,System::Double,System::Double,System::Double)
* M:Aspose::Page::Device::DrawRoundRect(System::Double,System::Double,System::Double,System::Double,System::Double,System::Double)
* M:Aspose::Page::Device::FillArc(System::Double,System::Double,System::Double,System::Double,System::Double,System::Double)
* M:Aspose::Page::Device::FillOval(System::Double,System::Double,System::Double,System::Double)
* M:Aspose::Page::Device::FillPolygon(System::ArrayPtr&lt;System::Int32&gt;,System::ArrayPtr&lt;System::Int32&gt;,System::Int32)
* M:Aspose::Page::Device::FillPolygon(System::ArrayPtr&lt;System::Double&gt;,System::ArrayPtr&lt;System::Double&gt;,System::Int32)
* M:Aspose::Page::Device::FillRect(System::Double,System::Double,System::Double,System::Double)
* M:Aspose::Page::Device::FillRoundRect(System::Double,System::Double,System::Double,System::Double,System::Double,System::Double)
* M:Aspose::Page::Device::CreateShape(System::ArrayPtr&lt;System::Int32&gt;,System::ArrayPtr&lt;System::Int32&gt;,System::Int32,System::Boolean)
* M:Aspose::Page::Device::CreateShape(System::ArrayPtr&lt;System::Double&gt;,System::ArrayPtr&lt;System::Double&gt;,System::Int32,System::Boolean)
* M:Aspose::Page::Device::ClearRect(System::Single,System::Single,System::Single,System::Single)
* M:Aspose::Page::Device::WriteBackground
* M:Aspose::Page::Device::WriteStroke(System::Drawing::Pen)
* M:Aspose::Page::Device::WriteWidth(System::Single)
* M:Aspose::Page::Device::HandleException(System::Exception)
* M:Aspose::Page::Device::WriteWarning(System::Exception)
* M:Aspose::Page::Device::WriteWarning(System::String)
* M:Aspose::Page::Device::WriteError(System::Exception)
* M:Aspose::Page::Device::WriteCap(System::Drawing::Drawing2D::LineCap)
* M:Aspose::Page::Device::WriteJoin(System::Drawing::Drawing2D::LineJoin)
* M:Aspose::Page::Device::WriteMiterLimit(System::Single)
* M:Aspose::Page::Device::WriteDash(System::ArrayPtr&lt;System::Double&gt;,System::Double,System::Drawing::Drawing2D::DashCap)
* M:Aspose::Page::Device::WritePaint(System::SharedPtr&lt;System::Drawing::SolidBrush&gt;)
* M:Aspose::Page::Device::WritePaint(System::SharedPtr&lt;System::Drawing::Drawing2D::LinearGradientBrush&gt;)
* M:Aspose::Page::Device::WritePaint(System::Drawing::Drawing2D::PathGradientBrush)
* M:Aspose::Page::Device::WritePaint(System::SharedPtr&lt;Aspose::Page::EPS::GradientBrush&gt;)
* M:Aspose::Page::Device::WritePaint(System::SharedPtr&lt;System::Drawing::TextureBrush&gt;)
* M:Aspose::Page::Device::WritePaint(System::SharedPtr&lt;System::Drawing::Brush&gt;)
* M:Aspose::Page::Device::WriteString(System::SharedPtr&lt;Aspose::Page::BaseTrFont&gt;,System::String)
* F:Aspose::Page::Device::creator
* F:Aspose::Page::Device::saveOptions
* F:Aspose::Page::Device::size
* F:Aspose::Page::Device::opacity
* F:Aspose::Page::Device::stroke
* F:Aspose::Page::Device::paint
* F:Aspose::Page::Device::opacityMask
* F:Aspose::Page::Device::font
* F:Aspose::Page::Device::charTM
* F:Aspose::Page::Device::textRenderingMode
* F:Aspose::Page::Device::textStrokeWidth
* F:Aspose::Page::Device::VERSION
* P:Aspose::Page::EPS::Device::ImageDevice::Format
* P:Aspose::Page::EPS::Device::ImageDevice::SaveOptions
* P:Aspose::Page::EPS::Device::ImageDevice::Creator
* P:Aspose::Page::EPS::Device::ImageDevice::Size
* P:Aspose::Page::EPS::Device::ImageDevice::Background
* P:Aspose::Page::EPS::Device::ImageDevice::Opacity
* P:Aspose::Page::EPS::Device::ImageDevice::Stroke
* P:Aspose::Page::EPS::Device::ImageDevice::Paint
* P:Aspose::Page::EPS::Device::ImageDevice::Font
* P:Aspose::Page::EPS::Device::ImageDevice::CharTM
* P:Aspose::Page::EPS::Device::ImageDevice::TextRenderingMode
* P:Aspose::Page::EPS::Device::ImageDevice::TextStrokeWidth
* P:Aspose::Page::EPS::Device::ImageDevice::IsDirectRGB
* M:Aspose::Page::EPS::Device::ImageDevice::ReNew
* M:Aspose::Page::EPS::Device::ImageDevice::GetProperty(System::String)
* M:Aspose::Page::EPS::Device::ImageDevice::GetPropertyColor(System::String)
* M:Aspose::Page::EPS::Device::ImageDevice::GetPropertyRectangle(System::String)
* M:Aspose::Page::EPS::Device::ImageDevice::GetPropertyMargins(System::String)
* M:Aspose::Page::EPS::Device::ImageDevice::GetPropertySize(System::String)
* M:Aspose::Page::EPS::Device::ImageDevice::GetPropertyInt(System::String)
* M:Aspose::Page::EPS::Device::ImageDevice::GetPropertyDouble(System::String)
* M:Aspose::Page::EPS::Device::ImageDevice::IsProperty(System::String)
* M:Aspose::Page::EPS::Device::ImageDevice::StartDocument
* M:Aspose::Page::EPS::Device::ImageDevice::EndDocument
* M:Aspose::Page::EPS::Device::ImageDevice::Dispose
* M:Aspose::Page::EPS::Device::ImageDevice::WriteBackground
* M:Aspose::Page::EPS::Device::ImageDevice::Reset
* M:Aspose::Page::EPS::Device::ImageDevice::Create
* M:Aspose::Page::EPS::Device::ImageDevice::InitClip
* M:Aspose::Page::EPS::Device::ImageDevice::Draw(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::EPS::Device::ImageDevice::Fill(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::EPS::Device::ImageDevice::DrawImage(System::Drawing::Bitmap,System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;,System::Drawing::Color)
* M:Aspose::Page::EPS::Device::ImageDevice::DrawString(System::String,System::Double,System::Double)
* M:Aspose::Page::EPS::Device::ImageDevice::GetTransform
* M:Aspose::Page::EPS::Device::ImageDevice::SetTransform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::EPS::Device::ImageDevice::Transform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::EPS::Device::ImageDevice::Translate(System::Double,System::Double)
* M:Aspose::Page::EPS::Device::ImageDevice::Rotate(System::Double)
* M:Aspose::Page::EPS::Device::ImageDevice::Scale(System::Double,System::Double)
* M:Aspose::Page::EPS::Device::ImageDevice::Shear(System::Double,System::Double)
* M:Aspose::Page::EPS::Device::ImageDevice::SetClip(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::EPS::Device::ImageDevice::WriteWidth(System::Single)
* M:Aspose::Page::EPS::Device::ImageDevice::WriteCap(System::Drawing::Drawing2D::LineCap)
* M:Aspose::Page::EPS::Device::ImageDevice::WriteJoin(System::Drawing::Drawing2D::LineJoin)
* M:Aspose::Page::EPS::Device::ImageDevice::WriteMiterLimit(System::Single)
* M:Aspose::Page::EPS::Device::ImageDevice::WriteDash(System::ArrayPtr&lt;System::Double&gt;,System::Double,System::Drawing::Drawing2D::DashCap)
* M:Aspose::Page::EPS::Device::ImageDevice::WritePaint(System::SharedPtr&lt;System::Drawing::SolidBrush&gt;)
* M:Aspose::Page::EPS::Device::ImageDevice::WritePaint(System::SharedPtr&lt;System::Drawing::Drawing2D::LinearGradientBrush&gt;)
* M:Aspose::Page::EPS::Device::ImageDevice::WritePaint(System::SharedPtr&lt;System::Drawing::TextureBrush&gt;)
* M:Aspose::Page::EPS::Device::ImageDevice::WritePaint(System::SharedPtr&lt;System::Drawing::Brush&gt;)
* M:Aspose::Page::EPS::Device::ImageDevice::WriteComment(System::String)
* M:Aspose::Page::EPS::Device::ImageDevice::WriteWarning(System::String)
* M:Aspose::Page::EPS::Device::ImageDevice::WriteString(System::SharedPtr&lt;Aspose::Page::BaseTrFont&gt;,System::String)
* M:Aspose::Page::EPS::Device::PdfDevice::#ctor(System::SharedPtr&lt;Aspose::Page::EPS::Device::PdfDevice&gt;,System::Boolean)
* P:Aspose::Page::EPS::Device::PdfDevice::Stroke
* P:Aspose::Page::EPS::Device::PdfDevice::Paint
* P:Aspose::Page::EPS::Device::PdfDevice::Font
* M:Aspose::Page::EPS::Device::PdfDevice::ReNew
* M:Aspose::Page::EPS::Device::PdfDevice::StartDocument
* M:Aspose::Page::EPS::Device::PdfDevice::EndDocument
* M:Aspose::Page::EPS::Device::PdfDevice::Dispose
* M:Aspose::Page::EPS::Device::PdfDevice::WriteBackground
* M:Aspose::Page::EPS::Device::PdfDevice::Reset
* M:Aspose::Page::EPS::Device::PdfDevice::UpdatePageParameters(System::SharedPtr&lt;IMultiPageDevice&gt;)
* M:Aspose::Page::EPS::Device::PdfDevice::Create
* M:Aspose::Page::EPS::Device::PdfDevice::InitClip
* M:Aspose::Page::EPS::Device::PdfDevice::Draw(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::EPS::Device::PdfDevice::Fill(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::EPS::Device::PdfDevice::DrawImage(System::SharedPtr&lt;System::Drawing::Bitmap&gt;,System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;,System::Drawing::Color)
* M:Aspose::Page::EPS::Device::PdfDevice::DrawString(System::String,System::Double,System::Double)
* M:Aspose::Page::EPS::Device::PdfDevice::GetTransform
* M:Aspose::Page::EPS::Device::PdfDevice::SetTransform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::EPS::Device::PdfDevice::Transform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::EPS::Device::PdfDevice::Translate(System::Double,System::Double)
* M:Aspose::Page::EPS::Device::PdfDevice::Rotate(System::Double)
* M:Aspose::Page::EPS::Device::PdfDevice::Scale(System::Double,System::Double)
* M:Aspose::Page::EPS::Device::PdfDevice::Shear(System::Double,System::Double)
* M:Aspose::Page::EPS::Device::PdfDevice::SetClip(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::EPS::Device::PdfDevice::WriteWidth(System::Single)
* M:Aspose::Page::EPS::Device::PdfDevice::WriteCap(System::Drawing::Drawing2D::LineCap)
* M:Aspose::Page::EPS::Device::PdfDevice::WriteJoin(System::Drawing::Drawing2D::LineJoin)
* M:Aspose::Page::EPS::Device::PdfDevice::WriteMiterLimit(System::Single)
* M:Aspose::Page::EPS::Device::PdfDevice::WriteDash(System::ArrayPtr&lt;System::Double&gt;,System::Double,System::Drawing::Drawing2D::DashCap)
* M:Aspose::Page::EPS::Device::PdfDevice::WritePaint(System::SharedPtr&lt;System::Drawing::SolidBrush&gt;)
* M:Aspose::Page::EPS::Device::PdfDevice::WritePaint(System::SharedPtr&lt;System::Drawing::Drawing2D::LinearGradientBrush&gt;)
* M:Aspose::Page::EPS::Device::PdfDevice::WritePaint(System::SharedPtr&lt;System::Drawing::TextureBrush&gt;)
* M:Aspose::Page::EPS::Device::PdfDevice::WritePaint(System::SharedPtr&lt;System::Drawing::Brush&gt;)
* M:Aspose::Page::EPS::Device::PdfDevice::WriteComment(System::String)
* M:Aspose::Page::EPS::Device::PdfDevice::WriteGraphicsState
* M:Aspose::Page::EPS::Device::PdfDevice::WriteWarning(System::String)
* M:Aspose::Page::EPS::Device::PdfDevice::WriteString(Aspose::Page::ITrFont,System::String)
* F:Aspose::Page::EPS::Device::PdfDevice::currentTransform
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::#ctor(System::SharedPtr&lt;Aspose::Page::XPS::Presentation::Image::ImageDevice&gt;)
* P:Aspose::Page::XPS::Presentation::Image::ImageDevice::SaveOptions
* P:Aspose::Page::XPS::Presentation::Image::ImageDevice::Size
* P:Aspose::Page::XPS::Presentation::Image::ImageDevice::Background
* P:Aspose::Page::XPS::Presentation::Image::ImageDevice::Opacity
* P:Aspose::Page::XPS::Presentation::Image::ImageDevice::Stroke
* P:Aspose::Page::XPS::Presentation::Image::ImageDevice::Paint
* P:Aspose::Page::XPS::Presentation::Image::ImageDevice::OpacityMask
* P:Aspose::Page::XPS::Presentation::Image::ImageDevice::Font
* P:Aspose::Page::XPS::Presentation::Image::ImageDevice::CurrentPageNumber
* P:Aspose::Page::XPS::Presentation::Image::ImageDevice::CurrentRelativePageNumber
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::ReNew
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::StartDocument
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::EndDocument
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::Reset
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::Create
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::Dispose
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::GetTransform
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::SetTransform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::Transform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::Translate(System::Double,System::Double)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::Rotate(System::Double)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::Scale(System::Double,System::Double)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::Shear(System::Double,System::Double)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::SetClip(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::WriteWidth(System::Single)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::WriteCap(System::Drawing::Drawing2D::LineCap)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::WriteJoin(System::Drawing::Drawing2D::LineJoin)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::WriteMiterLimit(System::Single)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::WriteDash(System::ArrayPtr&lt;System::Double&gt;,System::Double,System::Drawing::Drawing2D::DashCap)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::WritePaint(System::SharedPtr&lt;System::Drawing::SolidBrush&gt;)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::WritePaint(System::SharedPtr&lt;System::Drawing::Drawing2D::LinearGradientBrush&gt;)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::WritePaint(System::SharedPtr&lt;System::Drawing::TextureBrush&gt;)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::WritePaint(System::SharedPtr&lt;System::Drawing::Brush&gt;)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::Draw(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::Fill(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::XPS::Presentation::Image::ImageDevice::DrawString(System::String,System::Double,System::Double)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::#ctor(System::SharedPtr&lt;Aspose::Page::XPS::Presentation::Pdf::PdfDevice&gt;)
* P:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::SaveOptions
* P:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Size
* P:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Background
* P:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Opacity
* P:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Stroke
* P:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Paint
* P:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::OpacityMask
* P:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Font
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::ReNew
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::StartDocument
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::EndDocument
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Reset
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Create
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Dispose
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::GetTransform
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::SetTransform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Transform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Translate(System::Double,System::Double)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Rotate(System::Double)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Scale(System::Double,System::Double)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Shear(System::Double,System::Double)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::SetClip(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::WriteWidth(System::Single)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::WriteCap(System::Drawing::Drawing2D::LineCap)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::WriteJoin(System::Drawing::Drawing2D::LineJoin)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::WriteMiterLimit(System::Single)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::WriteDash(System::ArrayPtr&lt;System::Double&gt;,System::Double,System::Drawing::Drawing2D::DashCap)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::WritePaint(System::SharedPtr&lt;System::Drawing::SolidBrush&gt;)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::WritePaint(System::SharedPtr&lt;System::Drawing::Drawing2D::LinearGradientBrush&gt;)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::WritePaint(System::SharedPtr&lt;System::Drawing::TextureBrush&gt;)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::WritePaint(System::SharedPtr&lt;System::Drawing::Brush&gt;)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Draw(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::Fill(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::XPS::Presentation::Pdf::PdfDevice::DrawString(System::String,System::Double,System::Double)
* T:Aspose::Page::XPS::Presentation::Ps::PsDevice
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::#ctor(System::SharedPtr&lt;System::IO::Stream&gt;)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::#ctor(System::SharedPtr&lt;Aspose::Page::XPS::Presentation::Ps::PsDevice&gt;)
* P:Aspose::Page::XPS::Presentation::Ps::PsDevice::SaveOptions
* P:Aspose::Page::XPS::Presentation::Ps::PsDevice::Size
* P:Aspose::Page::XPS::Presentation::Ps::PsDevice::Background
* P:Aspose::Page::XPS::Presentation::Ps::PsDevice::Opacity
* P:Aspose::Page::XPS::Presentation::Ps::PsDevice::Stroke
* P:Aspose::Page::XPS::Presentation::Ps::PsDevice::Paint
* P:Aspose::Page::XPS::Presentation::Ps::PsDevice::OpacityMask
* P:Aspose::Page::XPS::Presentation::Ps::PsDevice::Font
* P:Aspose::Page::XPS::Presentation::Ps::PsDevice::CurrentPageNumber
* P:Aspose::Page::XPS::Presentation::Ps::PsDevice::CurrentRelativePageNumber
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::ReNew
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::StartDocument
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::EndDocument
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::Reset
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::InitPageNumbers
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::OpenPage(System::String)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::OpenPage(System::Single,System::Single)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::ClosePage
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::UpdatePageParameters(Aspose::Page::IMultiPageDevice)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::OpenPartition
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::ClosePartition
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::SetHyperlinkTarget(System::String)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::SetHyperlinkTarget(System::Int32)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::AddOutline(System::Int32,System::String)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::AddOutline(System::Drawing::PointF,System::Int32,System::String)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::Create
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::Dispose
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::GetTransform
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::SetTransform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::Transform(System::SharedPtr&lt;System::Drawing::Drawing2D::Matrix&gt;)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::Translate(System::Double,System::Double)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::Rotate(System::Double)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::Scale(System::Double,System::Double)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::Shear(System::Double,System::Double)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::SetClip(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::WriteWidth(System::Single)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::WriteCap(System::Drawing::Drawing2D::LineCap)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::WriteJoin(System::Drawing::Drawing2D::LineJoin)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::WriteMiterLimit(System::Single)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::WriteDash(System::ArrayPtr&lt;System::Double&gt;,System::Double,System::Drawing::Drawing2D::DashCap)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::WritePaint(System::SharedPtr&lt;System::Drawing::SolidBrush&gt;)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::WritePaint(System::SharedPtr&lt;System::Drawing::Drawing2D::LinearGradientBrush&gt;)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::WritePaint(System::SharedPtr&lt;System::Drawing::TextureBrush&gt;)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::WritePaint(System::SharedPtr&lt;System::Drawing::Brush&gt;)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::Draw(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::Fill(System::SharedPtr&lt;System::Drawing::Drawing2D::GraphicsPath&gt;)
* M:Aspose::Page::XPS::Presentation::Ps::PsDevice::DrawString(System::String,System::Double,System::Double)
* P:Aspose::Page::XPS::XpsDocument::Utils
* T:Aspose::Page::XPS::DocumentUtils
* M:Aspose::Page::XPS::DocumentUtils::CreateRectangle(System::Drawing::RectangleF)
* M:Aspose::Page::XPS::DocumentUtils::CreateEllipse(System::Drawing::PointF,System::Single,System::Single)
* M:Aspose::Page::XPS::DocumentUtils::CreateCircle(System::Drawing::PointF,System::Single)
* M:Aspose::Page::XPS::DocumentUtils::CreateRegularInscribedNGon(System::Int32,System::Drawing::PointF,System::Single)
* M:Aspose::Page::XPS::DocumentUtils::CreateRegularCircumscribedNGon(System::Int32,System::Drawing::PointF,System::Single)
* M:Aspose::Page::XPS::DocumentUtils::CreatePieSlice(System::Drawing::PointF,System::Single,System::Single,System::Single)
* M:Aspose::Page::XPS::DocumentUtils::CreateCircularSegment(System::Drawing::PointF,System::Single,System::Single,System::Single)
* M:Aspose::Page::XPS::DocumentUtils::CreateImage(System::String,System::Drawing::RectangleF,Aspose::Page::XPS::ImageMode)

You can consult Aspose.Page for C++ [API Reference](https://apireference.aspose.com/cpp/page/) for documentation.
