---
title: "각 컨트롤 크기 조정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b019cd2bbf68a4321bafd6dd960ffbcdba2dddf7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="sizing-individual-controls"></a>각 컨트롤 크기 조정
컨트롤의 크기를 조정 하려면 크기 조정 핸들을 사용 합니다. 크기 조정 핸들에 포인터를 컨트롤을 조정할 수 있는 지침을 나타내는 셰이프를 변경 됩니다. 현재 크기 조정 핸들은 실선입니다. 크기 조정 핸들을 빈 경우 해당 축을 따라 컨트롤을 조정할 수 없습니다.  
  
 컨트롤을 가이드 또는 여백, 맞춤 하 여 컨트롤의 크기를 변경할 수도 있습니다 또는 제어 및 안내선을 멀리 맞춘 이동 하 여 합니다.  
  
### <a name="to-size-a-control"></a>컨트롤 크기를 조정 하려면  
  
1.  컨트롤을 선택 합니다.  
  
2.  컨트롤의 크기를 변경 하려면 크기 조정 핸들을 끕니다.  
  
    -   위와 옆에 있는 크기 조정 핸들 가로 또는 세로 크기를 변경 합니다.  
  
    -   모퉁이에 크기 조정 핸들 가로 및 세로 크기를 변경 합니다.  
  
    > [!TIP]
    >  SHIFT 키를 누른 채 오른쪽 및 아래쪽 화살표 키를 사용 하 여 한 번에 하나의 대화 상자 단위 (DLU) 컨트롤을 조정할 수 있습니다.  
  
### <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>자동으로 내 텍스트에 맞게 컨트롤 크기 조정 하려면  
  
1.  선택 **콘텐츠 크기** 에서 **형식** 메뉴.  
  
 \- 또는 -  
  
-   컨트롤을 마우스 오른쪽 단추로 클릭 하 고 선택 **콘텐츠 크기** 바로 가기 메뉴에서.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)

