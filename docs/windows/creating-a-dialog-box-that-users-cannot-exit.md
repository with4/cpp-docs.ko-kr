---
title: 사용자가 종료할 수 없는 대화 상자 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, creating
- modal dialog boxes, logon screens
- logon screens
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc04c9ccfb0fdc74e57142bf746681411bbba495
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="creating-a-dialog-box-that-users-cannot-exit"></a>사용자가 종료할 수 없는 대화 상자 만들기
사용자가 종료할 수 없는 런타임 대화 상자를 만들 수 있습니다. 이 종류의 대화 상자는 로그온에 유용하며, 응용 프로그램 또는 문서를 잠그는 데에도 유용합니다.  
  
### <a name="to-create-a-dialog-box-that-a-user-cannot-exit"></a>사용자가 종료할 수 없는 대화 상자를 만들려면  
  
1.  대화 상자의 **속성** 창에서 **시스템 메뉴** 속성을 **false**로 설정합니다.  
  
     이렇게 하면 대화 상자의 시스템 메뉴 및 **닫기** 단추가 비활성화됩니다.  
  
2.  대화 상자 폼에서 **취소** 및 **확인** 단추를 삭제합니다.  
  
     런타임 시 사용자는 이러한 특징이 있는 모달 대화 상자를 종료할 수 없습니다.  
  
 이러한 종류의 대화 상자를 테스트할 수 있도록 테스트 대화 상자에는 ESC 키가 눌러지는 경우를 감지하는 기능이 있습니다. (ESC는 VK_ESCAPE 가상 키라고도 합니다.) 런타임 시 대화 상자가 어떻게 동작하도록 설계되었는지와 관계없이 테스트 모드에서는 ESC 키를 누르면 대화 상자를 종료할 수 있습니다.  
  
> [!NOTE]
>  MFC 응용 프로그램의 경우 사용자가 종료할 수 없는 대화 상자를 만들려면 `OnOK` 및 `OnCancel` 의 기본 동작을 재정의해야 합니다. 관련된 단추를 삭제하더라도 Enter 또는 ESC 키를 누르면 여전히 대화 상자를 닫을 수 있기 때문입니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하십시오. [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [방법: 리소스 만들기](../windows/how-to-create-a-resource.md)   
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [대화 상자 편집기](../windows/dialog-editor.md)

