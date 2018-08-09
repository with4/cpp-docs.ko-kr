---
title: 그리기 도구 (아이콘에 대 한 이미지 편집기)를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.drawing
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], selecting drawing tools
- Image editor [C++], toolbar
- drawing tools
ms.assetid: 1f8c6eef-7760-45a9-a5cb-9e15c6f91245
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8345829e5d561ead3be0052770e022f704eabc3b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646126"
---
# <a name="using-a-drawing-tool-image-editor-for-icons"></a>그리기 도구 사용(아이콘에 대한 이미지 편집기)
이미지 편집기의 자유롭게 그리기 및 지우기 도구 동일한 방식으로 작동: 도구를 선택 하 고 필요한 경우 [전경색 및 배경색을 선택](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) 크기 및 모양 옵션. 다음 이미지에 포인터를 이동 하 고 클릭 하거나 그리기 및 지우기으로 끌어 옵니다.  
  
 선택 하는 경우는 **지우개** 도구인 **브러시** 도구인 또는 **에 어 브러시** 도구, 옵션 선택기에는 해당 도구의 옵션이 표시 됩니다.  
  
> [!TIP]
>  사용 하는 대신 합니다 **지우개** 도구인 있습니다 더 편리할 수 것 그리기 도구 중 하나를 사용 하 여 배경색으로 그리는 것입니다.  
  
 그리기 도구 중에서 선택할 수 있습니다 합니다 **이미지 편집기** 도구 모음 또는 **이미지** 메뉴.  
  
### <a name="to-select-and-use-a-drawing-tool-from-the-image-editor-toolbar"></a>선택 하 고 이미지 편집기 도구 모음에서 그리기 도구 사용  
  
1.  단추를 클릭 합니다 **이미지 편집기** 도구 모음입니다.  
  
    -   합니다 **지우개** 마우스 왼쪽된 단추를 누를 때 현재 배경색을 사용 하 여 이미지 그리기 도구입니다.  
  
    -   합니다 **연필** 도구 상수 1 픽셀 너비의 자유형 그립니다.  
  
    -   합니다 **브러시 도구의 모양 및 크기를 결정 하는 옵션 선택기**합니다.  
  
    -   합니다 **에 어 브러시** 도구 색 픽셀 브러시의 중심을 임의로 분산 합니다.  
  
        > [!TIP]
        >  단추 위에 커서를 올려 놓으면 도구 설명이 표시 합니다 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md)합니다. 이러한 팁은 여기에 언급 된 특정 단추를 식별 하는 데 도움이 됩니다.  
  
2.  필요한 경우 색상 및 브러시를 선택 합니다.  
  
    -   에 [색상표](../windows/colors-window-image-editor-for-icons.md), 전경색을 선택 하려면 마우스 왼쪽된 단추 또는 배경 색을 선택 하려면 마우스 오른쪽 단추를 클릭 합니다.  
  
    -   에 [옵션 선택기](../windows/toolbar-image-editor-for-icons.md), 사용 하려는 브러시를 나타내는 셰이프를 클릭 합니다.  
  
3.  그리기 또는 이미지 그리기를 시작 하려는 위치를 가리킵니다. 포인터는 선택한 도구에 따라 셰이프를 변경 합니다.  
  
4.  (전경색)에 대 한 왼쪽된 마우스 단추를 누르거나 (배경색)에 대 한 마우스 오른쪽 단추를 누른 상태로 그리기 합니다.  
  
### <a name="to-select-and-use-a-drawing-tool-from-the-image-menu"></a>선택 하 고 이미지 메뉴에서 그리기 도구 사용  
  
1.  클릭 합니다 **이미지** 메뉴를 선택 합니다 **도구** 명령입니다.  
  
2.  연계 하위 메뉴를 사용 하려면이 도구를 선택 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)   
 [색 작업](../windows/working-with-color-image-editor-for-icons.md)