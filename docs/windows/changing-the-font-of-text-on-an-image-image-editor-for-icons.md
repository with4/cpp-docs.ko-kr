---
title: 이미지 (아이콘에 대 한 이미지 편집기)의 텍스트 글꼴 변경 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- fonts, changing on an image
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 16d01d634b44b4e6da425c40e011106021638305
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461740"
---
# <a name="changing-the-font-of-text-on-an-image-image-editor-for-icons"></a>이미지의 텍스트 글꼴 변경(아이콘에 대한 이미지 편집기)
다음 절차는 하는 방법의 예:  
  
-   Windows 응용 프로그램의 아이콘에 텍스트 추가  
  
-   텍스트의 글꼴 조작  
  
### <a name="to-change-the-font-of-text-on-an-image"></a>이미지의 텍스트의 글꼴을 변경 하려면  
  
1.  C + + Windows Forms 응용 프로그램을 만듭니다. 자세한 내용은 참조 하세요 [Windows 응용 프로그램 프로젝트를 만드는](http://msdn.microsoft.com/b2f93fed-c635-4705-8d0e-cf079a264efa)합니다. 합니다 [Windows Forms 응용 프로그램 템플릿을](http://msdn.microsoft.com/1babdebf-ab3f-4a64-a608-98499a5b9cea) 기본적으로 프로젝트에 app.ico 라는 파일을 추가 합니다.  
  
2.  솔루션 탐색기에서 app.ico 파일을 두 번 클릭 합니다. 합니다 [이미지 편집기](../windows/image-editor-for-icons.md) 열립니다.  
  
3.  **이미지** 메뉴에서 **도구** 선택한 후 **텍스트 도구**합니다. 합니다 [텍스트 도구 대화 상자](../windows/text-tool-dialog-box-image-editor-for-icons.md) 나타납니다.  
  
4.  에 **텍스트 도구** 대화 상자에서 `C++` 빈 텍스트 영역에 있습니다. 이 텍스트에 app.ico의 왼쪽된 위 모퉁이 크기를 조정할 수 상자에 표시 됩니다는 **이미지 편집기**합니다.  
  
5.  에 **이미지 편집기**, 크기를 조정할 수 상자 텍스트의 가독성을 높이기 위해 app.ico의 가운데로 끕니다.  
  
6.  에 **텍스트 도구** 대화 상자에서 클릭 합니다 **글꼴** 단추입니다. 합니다 [텍스트 도구 글꼴 대화 상자](../windows/text-tool-font-dialog-box-image-editor-for-icons.md) 나타납니다.  
  
7.  에 **텍스트 도구 글꼴** 대화 상자에서 **Times New Roman** 에 나와 있는 사용 가능한 글꼴 목록에서를 **글꼴** 목록 상자입니다.  
  
8.  선택 **굵게** 에 나열 된 사용 가능한 글꼴 스타일 목록을 합니다 **글꼴 스타일** 목록 상자입니다.  
  
9. 선택 **10** 지점에 나열 된 크기의 사용 가능한 목록의 합니다 **크기** 목록 상자입니다.  
  
10. 클릭 합니다 **확인** 단추입니다. 합니다 **텍스트 도구 글꼴** 대화 상자가 닫히고 새 글꼴 설정을 텍스트에 적용 됩니다.  
  
11. 클릭 합니다 **닫습니다** 단추를 **텍스트 도구** 대화 상자. 텍스트 주위의 크기를 조정할 수 상자는 이미지 편집기에서 사라집니다.  
  
## <a name="see-also"></a>참고 항목  
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [도구 모음](../windows/toolbar-image-editor-for-icons.md)