---
title: (아이콘에 대 한 이미지 편집기) 사용자 지정 브러시 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fa6b10f1d263db95bf6eb901e65a3111721d6226
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647975"
---
# <a name="creating-a-custom-brush-image-editor-for-icons"></a>사용자 지정 브러시 만들기(아이콘에 대한 이미지 편집기)
사용자 지정 브러시는 선택 하 고와 같이 사용할 수 있는 이미지의 사각형 부분을 **이미지** 편집기의 바로 사용할 수 있는 브러시입니다. 선택 영역에서 수행할 수 있는 모든 작업을 사용자 지정 브러시도 수행할 수 있습니다.  
  
### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>이미지의 일부에서 사용자 지정 브러시를 만들려면  
  
1.  [이미지의 일부 선택](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) 브러시에 사용 하려는.  
  
2.  보유 하는 **Shift** 아래로 키 선택 영역을 클릭 하 고 이미지를 끕니다.  
  
     \- 또는 -  
  
3.  **이미지** 메뉴 선택 **사용 하 여 선택 항목을 브러시로**합니다.  
  
     선택한은 이미지에 색 선택 영역에 분산 하는 사용자 지정 브러시 됩니다. 선택 항목의 복사본은 끌기 경로 남아 있습니다. 끌면 더 느린, 많은 복사본이 만들어집니다.  
  
     > [!NOTE]
     > 클릭 하 여 **브러시로 사용** 먼저 이미지의 부분의 선택 하는 전체 이미지를 브러시로 사용 하지 않고 합니다. 사용자 지정 브러시를 사용 하면 선택 하는지에 따라 달라 집니다를 [불투명 또는 투명 한 배경을](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)합니다.  
  
 현재 배경색을 일치 하는 사용자 지정 브러시 픽셀은 일반적으로 투명 한: 기존 이미지 그리지 않습니다. 기존 이미지 그리기 배경색 픽셀 수 있도록이 동작을 변경할 수 있습니다.  
  
 다양 한 특수 효과 만들려면 스탬프 또는 스텐실와 같은 사용자 지정 브러시를 사용할 수 있습니다.  
  
### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>배경색에 사용자 지정 브러시 모양을 그리는  
  
1.  [불투명 또는 투명 한 배경을 선택](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)합니다.  
  
2.  [배경색 설정](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) 그릴 원하는 색으로 합니다.  
  
3.  그리기를 사용자 지정 브러시를 배치 합니다.  
  
4.  마우스 오른쪽 단추를 클릭 합니다. 사용자 지정 브러시의 모든 불투명 영역 배경색에 그려집니다.  
  
### <a name="to-double-or-halve-the-custom-brush-size"></a>두 번 또는 사용자 지정 브러시 크기를 절반으로 줄일  
  
1.  키를 눌러 합니다 **더하기** (**+**) 브러시 크기를 두 배로 키 또는 **빼기 기호** (**-**) 키를이 절반으로 줄일 .  
  
### <a name="to-cancel-the-custom-brush"></a>사용자 지정 브러시를 취소 하려면  
  
1.  키를 눌러 **Esc** 하거나 다른 그리기 도구를 선택 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)