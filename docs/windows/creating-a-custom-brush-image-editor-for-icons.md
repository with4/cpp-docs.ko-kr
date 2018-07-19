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
ms.openlocfilehash: a879850c00957568065150b6c6fc1c801c049fa2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873149"
---
# <a name="creating-a-custom-brush-image-editor-for-icons"></a>사용자 지정 브러시 만들기(아이콘에 대한 이미지 편집기)
사용자 지정 브러시는를 선택 하 고 하나는 이미지 편집기의 포함 되어 있는 브러시와 같은 사용 되는 이미지의 사각형 부분입니다. 선택 영역에서 수행할 수는 모든 작업을 사용자 지정 브러시에 수행할 수 있습니다.  
  
### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>이미지의 부분에서 사용자 지정 브러시를 만들려면  
  
1.  [이미지의 일부 선택](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) 브러시로 사용 하려는.  
  
2.  보유 된 **SHIFT** 아래로 키을 선택 영역에서 클릭 한 다음 이미지에서 끌어 합니다.  
  
     \- 또는 -  
  
3.  **이미지** 메뉴 선택 **브러시로 사용 하 여 선택 영역**합니다.  
  
     선택한은 이미지에서 선택 영역에 색을 배포 하는 사용자 지정 브러시 됩니다. 선택 항목의 복사본 끌기 경로 남아 있습니다. 끌면 느리게, 많은 복사본이 만들어집니다.  
  
     **참고** 클릭은 **브러시로 선택 영역을 사용 하 여** 없이 먼저 이미지의 부분의 선택 하는 브러시 속성으로 전체 이미지를 사용 합니다. 사용자 지정 브러시를 사용 하 여 결과에 따라 다릅니다 선택 하는지에 [투명 또는 불투명 배경](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)합니다.  
  
 현재 배경색과 일치 하는 사용자 지정 브러시 픽셀은 일반적으로 투명 하 게: 기존 이미지 그리지 않습니다. 기존 이미지 위에 그려집니다 배경색 픽셀 되도록이 동작을 변경할 수 있습니다.  
  
 다양 한 특수 효과 만들 스탬프 또는 스텐실 같은 사용자 지정 브러시를 사용할 수 있습니다.  
  
#### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>명령 프롬프트 창의 배경색에 사용자 지정 브러시 도형을 그릴  
  
1.  [투명 또는 불투명 배경 선택](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)합니다.  
  
2.  [명령 프롬프트 창의 배경색 설정](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) 를 그리는 데 사용할 색입니다.  
  
3.  그리기를 사용자 지정 브러시를 배치 합니다.  
  
4.  마우스 오른쪽 단추를 클릭 합니다. 사용자 지정 브러시의 불투명 영역이 배경색에 그려집니다.  
  
#### <a name="to-double-or-halve-the-custom-brush-size"></a>두 번 또는 사용자 지정 브러시 크기를 절반으로 줄일  
  
1.  키를 눌러는 **더하기 기호** (**+**) 브러시 크기를 두 배로 키 또는 **빼기 기호** (**-**) 키 것를 절반으로 줄일를 .  
  
#### <a name="to-cancel-the-custom-brush"></a>사용자 지정 브러시를 취소 하려면  
  
1.  키를 눌러 **ESC** 하거나 다른 그리기 도구를 선택 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
### <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)

