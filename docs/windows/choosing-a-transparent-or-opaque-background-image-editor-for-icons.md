---
title: 투명 또는 불투명 배경 (아이콘에 대 한 이미지 편집기)를 선택 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- opaque backgrounds
- background colors, images
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- background images
- images [C++], transparency
- images [C++], opaque background
- transparent backgrounds
- transparency, background
- transparent backgrounds, images
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c8a809e7cd7ed7a461149707cc9e0b2a4a62158
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649522"
---
# <a name="choosing-a-transparent-or-opaque-background-image-editor-for-icons"></a>투명 또는 불투명 배경 선택(아이콘에 대한 이미지 편집기)
을 이동 하거나 이미지에서 선택 항목을 복사 하는 경우 현재 배경색을 일치 하는 모든 픽셀 선택 영역에는, 기본적으로 투명 합니다. 대상 위치에 픽셀을 숨깁니다 하지 않습니다.  
  
 불투명 한 배경으로 투명 한 배경을 (기본값)에서 전환 하 고 다시 수 있습니다. 선택 도구를 사용 하는 경우는 **투명 한 배경을** 및 **불투명 한 배경** 옵션에 표시 합니다 **옵션** 선택기는 **이미지 편집기** 도구 모음 (아래와 같이).  
  
 ![배경 옵션 &#45; 불투명 또는 투명](../windows/media/vcimageeditoropaqtranspback.gif "vcImageEditorOpaqTranspBack")  
**투명 한 픽셀과 불투명 한 옵션** 에 **이미지 편집기 도구 모음**  
  
### <a name="to-switch-between-a-transparent-and-opaque-background"></a>투명 한 픽셀과 불투명 한 배경 사이 전환 하려면  
  
1.  에 **이미지 편집기** 도구 모음에서 클릭 합니다 **옵션** 선택기 적절 한 배경을 클릭 하 고:  
  
    -   `Opaque Background (O)`: 기존 이미지를 선택 영역의 모든 부분이 가립니다.  
  
    -   `Transparent Background (T)`: 현재 배경색을 일치 하는 선택 영역의 부분 기존 이미지 보여 줍니다.  
  
 \- 또는 -  
  
-   에 **이미지** 메뉴에서 선택 하거나 선택을 취소 **불투명 하 게 그리기**합니다.  
  
 이미지의 어느 요소가 투명 하 게 변경 효과에 이미 선택 하는 동안 배경색을 변경할 수 있습니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [색 작업](../windows/working-with-color-image-editor-for-icons.md)