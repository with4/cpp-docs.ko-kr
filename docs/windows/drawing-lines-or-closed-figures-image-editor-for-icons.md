---
title: 선 또는 닫힌된 그림 (아이콘에 대 한 이미지 편집기)를 그리기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- closed figures, drawing
- lines [C++], painting
- lines [C++], drawing
- Image editor [C++], drawing lines
- shapes, drawing
ms.assetid: 7edd86db-77b1-451f-8001-bbfed9c6304f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6e2defbde7963c6e58cdfe3f4a25ea550ad88e5f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="drawing-lines-or-closed-figures-image-editor-for-icons"></a>선 또는 닫힌 그림 그리기(아이콘에 대한 이미지 편집기)
선 그리기에 대 한 이미지 편집기 도구와 동일한 방식으로 닫힌된 그림 작동: 한 지점에 삽입 포인터를 두고 다른 위치로 끕니다. 줄에 대 한 이러한 포인트는 끝점입니다. 닫힌된 그림에 대 한 이러한 지점은 그림 경계 사각형의 모서리를 반대 됩니다.  
  
 현재 브러시 선택 때 결정에서 선이 그려집니다 및 프레임된 수치 현재 두께 선택할 때 결정에 그려집니다. 선 및 모든 figures 인 경우 모두 프레임 및 가득 차면 그려집니다 마우스 왼쪽된 단추를 누르면 현재 전경색 또는 배경색 현재 마우스 오른쪽 단추를 누를 경우.  
  
### <a name="to-draw-a-line"></a>선 그리기  
  
1.  에 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md) (또는 **이미지** 메뉴 **도구** 명령)을 클릭는 **줄** 도구입니다.  
  
2.  필요에 따라 색과 브러시를 선택 합니다.  
  
    -   에 [색상표](../windows/colors-window-image-editor-for-icons.md), 전경색을 선택 하려면 마우스 왼쪽된 단추 또는 배경색 선택 하려면 마우스 오른쪽 단추를 클릭 합니다.  
  
    -   에 [옵션 선택기](../windows/toolbar-image-editor-for-icons.md)를 사용 하려는 브러시를 나타내는 셰이프를 클릭 합니다.  
  
3.  선의 시작점에 포인터를 놓습니다.  
  
4.  선 끝점을 끕니다.  
  
### <a name="to-draw-a-closed-figure"></a>닫힌된 그림 그리기를  
  
1.  에 **이미지 편집기** 도구 모음 (또는 **이미지** 메뉴 **도구** 명령)을 클릭는 **닫힌 그림 그리기** 도구입니다.  
  
     **닫힌 그림 그리기** 도구는 각 단추에 표시 된 대로 그림을 만듭니다.  
  
2.  필요에 따라 색과 선 두께 선택 합니다.  
  
3.  그림을 그릴 사각형 영역의 모서리 하나에 포인터를 이동 합니다.  
  
4.  포인터 대각선 방향으로 반대 모서리를 끕니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 요구 사항  
  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)   
 [색 작업](../windows/working-with-color-image-editor-for-icons.md)

