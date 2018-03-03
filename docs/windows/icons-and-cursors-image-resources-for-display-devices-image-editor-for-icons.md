---
title: "아이콘 및 커서: 디스플레이 장치 (아이콘에 대 한 이미지 편집기)에 대 한 이미지 리소스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], creating
- image resources, display devices
- icons [C++], creating
- cursors [C++], types
- icons [C++]
- Image editor [C++], icons and cursors
- cursors [C++]
- display devices, creating icons for
- cursors [C++], hot spots
- icons [C++], types
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99ed2e99c3a08b473dcc786ed47bc088b8fd8a4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons"></a>아이콘 및 커서: 디스플레이 장치용 이미지 리소스(아이콘에 대한 이미지 편집기)
아이콘 및 커서는 다양한 유형의 디스플레이 장치에 맞는 다양한 크기 및 색 구성표의 여러 이미지를 포함할 수 있는 그래픽 리소스입니다. 또한 커서에는 Windows에서 해당 위치를 추적하는 데 사용하는 위치인 "핫스팟"이 있습니다. 비트맵 및 기타 이미지와 마찬가지로 아이콘과 커서는 모두 이미지 편집기를 사용하여 생성하고 편집할 수 있습니다.  
  
 새 아이콘 또는 커서를 만들 때 이미지 편집기는 먼저 표준 형식의 이미지를 만듭니다. 이미지는 처음에 투명한 화면 색상으로 채워집니다. 이미지가 커서인 경우 핫스팟은 처음에 왼쪽 위 모서리(좌표 0, 0)에 있습니다.  
  
 기본적으로 이미지 편집기는 다음 표에 표시된 장치의 추가 이미지 만들기를 지원합니다. [사용자 지정 이미지 대화 상자](custom-image-dialog-box-image-editor-for-icons.md)에 너비, 높이 및 색상 수 매개 변수를 입력하여 기타 장치의 이미지를 만들 수 있습니다.  
  
> [!NOTE]
>  이미지 편집기를 사용하여 32비트 이미지를 볼 수는 있지만 편집할 수는 없습니다.  
  
|색|너비(픽셀)|높이(픽셀)|  
|-----------|----------------------|-----------------------|  
|단색|16|16|  
|단색|32|32|  
|단색|48|48|  
|단색|64|64|  
|단색|96|96|  
|16|16|16|  
|16|32|32|  
|16|64|64|  
|16|48|48|  
|16|96|96|  
|256|16|16|  
|256|32|32|  
|256|48|48|  
|256|64|64|  
|256|96|96|  
  
-   [새 장치 이미지 만들기(아이콘 또는 커서)](../windows/creating-a-device-image-image-editor-for-icons.md)  
  
-   [다른 디스플레이 장치용 이미지 추가](../windows/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)  
  
-   [장치 이미지 복사](../windows/copying-a-device-image-image-editor-for-icons.md)  
  
-   [장치 이미지 삭제](../windows/deleting-a-device-image-image-editor-for-icons.md)  
  
-   [장치 이미지에서 투명한 영역이나 반전 영역 만들기](../windows/creating-transparent-or-inverse-regions-in-device-images.md)  
  
-   [256색 아이콘이나 커서 만들기](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)  
  
-   [커서의 핫스팟 설정](../windows/setting-a-cursor-s-hot-spot-image-editor-for-icons.md)  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)   
 [아이콘](http://msdn.microsoft.com/library/windows/desktop/ms646973)   
 [커서](http://msdn.microsoft.com/library/windows/desktop/ms646970)

