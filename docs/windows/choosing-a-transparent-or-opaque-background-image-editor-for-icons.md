---
title: (아이콘에 대 한 이미지 편집기)는 투명 또는 불투명 배경 선택 | Microsoft Docs
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
ms.openlocfilehash: 244e6a63bc16b5e83bb8419dbe1b53741d566e56
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857914"
---
# <a name="choosing-a-transparent-or-opaque-background-image-editor-for-icons"></a>투명 또는 불투명 배경 선택(아이콘에 대한 이미지 편집기)
때을 이동 하거나 이미지에서 선택 영역 복사 현재 배경색을 일치 하는 모든 픽셀 선택 영역에는 기본적으로 선택 합니다. 대상 위치에서 픽셀을 숨깁니다 하지 않습니다.  
  
 불투명 한 배경, 투명 한 배경 (기본값)에서 전환 및 복귀 수 있습니다. 선택 도구를 사용 하는 경우는 **투명 한 배경** 및 **불투명 한 배경** 에 옵션 선택기에 옵션이 표시 된 **이미지 편집기** 도구 모음 (아래와 같이).  
  
 ![배경 옵션 &#45; 불투명 또는 투명](../windows/media/vcimageeditoropaqtranspback.gif "vcImageEditorOpaqTranspBack")  
이미지 편집기 도구 모음에서 투명 하 고 불투명 옵션  
  
### <a name="to-switch-between-a-transparent-and-opaque-background"></a>투명 하 고 불투명 한 배경 사이 전환 하려면  
  
1.  에 **이미지 편집기** 도구 모음에서 클릭 된 **옵션** 선택기를 다음 원하는 배경을 클릭 하 고:  
  
    -   **불투명 한 배경 (O)**: 기존 이미지는 선택 항목의 모든 부분에서 가려집니다.  
  
    -   **투명 한 배경 (T)**: 기존 이미지는 선택 항목의 현재 배경색과 일치 하는 부분 위에 표시 합니다.  
  
 \- 또는 -  
  
-   에 **이미지** 메뉴에서 선택 하거나 선택 취소 **불투명 하 게 그리기**합니다.  
  
 선택이 이미 적용 이미지의 부분 투명 하 게 변경 하려면 명령 프롬프트 창의 배경색을 변경할 수 있습니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 요구 사항  
  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [색 작업](../windows/working-with-color-image-editor-for-icons.md)