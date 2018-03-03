---
title: "그리기 도구 (아이콘에 대 한 이미지 편집기)를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.image.drawing
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], selecting drawing tools
- Image editor [C++], toolbar
- drawing tools
ms.assetid: 1f8c6eef-7760-45a9-a5cb-9e15c6f91245
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a2f6d310bedd3a2a523112d57ece2dcc54fb3fd1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-drawing-tool-image-editor-for-icons"></a>그리기 도구 사용(아이콘에 대한 이미지 편집기)
이미지 편집기의 자유 그리기 및 지우기 동일한 방식으로 작동 하는 도구: 도구를 선택 하 고, 필요한 경우 [전경색과 배경색을 선택](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) 및 크기와 셰이프 옵션. 다음 이미지에 포인터를 이동 하 고를 클릭 하거나 끈 도형 그리기 및 지우기입니다.  
  
 선택 하는 경우는 **지우개** 도구를 **브러시** 도구 또는 **어 브러시** 도구, 옵션 선택기 해당 도구의 옵션을 표시 합니다.  
  
> [!TIP]
>  사용 하는 대신는 **지우개** 도구를 알게 될 수 있습니다이 그리기 도구 중 하나를 사용 하 여 배경색으로 그릴 합니다.  
  
 그리기 도구 중 하나에서 선택할 수 있습니다는 **이미지 편집기** 도구 모음 또는 **이미지** 메뉴.  
  
### <a name="to-select-and-use-a-drawing-tool-from-the-image-editor-toolbar"></a>선택 하 고 이미지 편집기 도구 모음에서 그리기 도구 사용  
  
1.  단추만 클릭는 **이미지 편집기** 도구 모음입니다.  
  
    -   **지우개** 마우스 왼쪽된 단추를 누를 때 현재 배경색으로 이미지 그리기 도구입니다.  
  
    -   **연필** 도구 자유롭게 1 픽셀씩 상수 너비 그릴 합니다.  
  
    -   **브러시 도구 모양과 크기를 결정 하는 옵션 선택기**합니다.  
  
    -   **어 브러시** 도구 색 픽셀 브러시의 중심을 임의로 분산 합니다.  
  
        > [!TIP]
        >  단추 위에 커서를 올려 놓으면 도구 설명이 표시는 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md)합니다. 이러한 팁은 여기에 언급 된 특정 단추를 식별 하는 데 도움이 됩니다.  
  
2.  필요에 따라 색과 브러시를 선택 합니다.  
  
    -   에 [색상표](../windows/colors-window-image-editor-for-icons.md), 전경색을 선택 하려면 마우스 왼쪽된 단추 또는 배경색 선택 하려면 마우스 오른쪽 단추를 클릭 합니다.  
  
    -   에 [옵션 선택기](../windows/toolbar-image-editor-for-icons.md)를 사용 하려는 브러시를 나타내는 셰이프를 클릭 합니다.  
  
3.  이미지를 그리기 또는 그리기의 위치를 가리킵니다. 포인터에는 선택한 도구에 따라 모양이 변경 됩니다.  
  
4.  (전경색)에 대 한 마우스 왼쪽된 단추를 클릭 하거나 (용 배경색)를 마우스 오른쪽 단추로 누른 상태로 그리기.  
  
### <a name="to-select-and-use-a-drawing-tool-from-the-image-menu"></a>선택 하 고 이미지 메뉴에서 그리기 도구 사용  
  
1.  클릭는 **이미지** 메뉴를 선택은 **도구** 명령입니다.  
  
2.  연계 하위 메뉴에 사용 하려는 도구를 선택 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 요구 사항  
  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)   
 [색 작업](../windows/working-with-color-image-editor-for-icons.md)

