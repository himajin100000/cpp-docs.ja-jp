---
title: priority_queue::difference_type (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::priority_queue::difference_type
dev_langs:
- C++
helpviewer_keywords:
- difference_type member [STL/CLR]
ms.assetid: 4bedce11-244c-428b-b5e2-e6bbf5674803
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a918bf5317c99fcd62854b17dad8929d3a8ad6a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueuedifferencetype-stlclr"></a>priority_queue::difference_type (STL/CLR)
2 つの要素間の距離を符号付きの型。  
  
## <a name="syntax"></a>構文  
  
```  
typedef int difference_type;  
```  
  
## <a name="remarks"></a>コメント  
 この型は、可能性のある負の値の要素の数を表します。  
  
## <a name="example"></a>例  
  
```  
// cliext_priority_queue_difference_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute negative difference   
    Mypriority_queue::difference_type diff = c1.size();   
    c1.push(L'd');   
    c1.push(L'e');   
    diff -= c1.size();   
    System::Console::WriteLine("pushing 2 = {0}", diff);   
  
// compute positive difference   
    diff = c1.size();   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    diff -= c1.size();   
    System::Console::WriteLine("popping 3 = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
pushing 2 = -2  
popping 3 = 3  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::size_type (STL/CLR)](../dotnet/priority-queue-size-type-stl-clr.md)