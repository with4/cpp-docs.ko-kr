---
title: "대화 상자의 크기와 위치를 지정 합니다. | Microsoft Docs"
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
- dialog boxes, size
- dialog boxes, positioning
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 03c4c6d6afb13a0e4ed8801838356ff0d1e851f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-the-location-and-size-of-a-dialog-box"></a>대화 상자의 위치와 크기 지정
대화 상자 단위와 위치 대화 상자에서으로 위치의 크기와 안에 있는 컨트롤의 크기 측정 됩니다. 개별 컨트롤 및 대화 상자에 대 한 값은 Visual Studio 상태를 선택 하면 표시줄의 오른쪽 아래에 나타납니다.  
  
 세 가지 속성에 설정할 수 있는 [속성 창](/visualstudio/ide/reference/properties-window) 대화 상자가 화면 상에 위치를 지정할 수 있습니다. 센터 속성은 부울입니다. 값을 True로 설정 하면 대화 상자 항상 화면 중앙에 나타납니다. False로 설정 하는 경우 Xpo와 YPos 속성 화면 대화 상자를 표시할 위치를 명시적으로 정의 하려면 다음 설정할 수 있습니다. 위치 속성은 {X = 0, Y = 0}로 정의 된 보기 영역의 왼쪽 위 모서리에서 오프셋된 값입니다. 위치를 기준는 **Absolute Align** 속성: 좌표는 화면에 대해 true 이면; 대화 상자 사용자 창을 기준으로 한 좌표 False 인 경우.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)

