# Numpy

## Install


```
#Terminal
pip3 install numpy --upgrade

#Jupyter Notebook
!pip3 install numpy --upgrade
```

    Requirement already up-to-date: numpy in /usr/local/lib/python3.7/site-packages (1.17.4)


## Import


```python
import numpy as np
```

## Create Array

#### Numpy array from an array


```python
array_first = np.array([1,2,3,4])
array_first
```




    array([1, 2, 3, 4])




```python
numbers = [6,7,8,9]
array_second = np.array(numbers)
array_second
```




    array([6, 7, 8, 9])



#### Numpy array initialize with zeroes


```python
array_third = np.zeros((2,3))
array_third
```




    array([[0., 0., 0.],
           [0., 0., 0.]])



#### Numpy array initialize with ones


```python
array_ones = np.ones((2,3))
array_ones
```




    array([[1., 1., 1.],
           [1., 1., 1.]])



#### Numpy array initialize with datatype


```python
array_ones_int = np.ones((2,3),dtype=np.int16)
array_ones_int
```




    array([[1, 1, 1],
           [1, 1, 1]], dtype=int16)



#### Numpy create an empty array


```python
# Create new uninitialized array
array_empty = np.empty((2, 2))
array_empty
```




    array([[-0.00000000e+000, -2.00389210e+000],
           [ 9.88131292e-324,  2.82464337e-309]])



#### Create diagonal array


```python
# create 1 in diagonal and 0 else
array_eye = np.eye(3)
array_eye
```




    array([[1., 0., 0.],
           [0., 1., 0.],
           [0., 0., 1.]])



#### Generate new array with interval


```python
# 1 - start value
# 20 - end value
# 2 - step value
array_of_odds = np.arange(1,20,2)
array_of_odds
```




    array([ 1,  3,  5,  7,  9, 11, 13, 15, 17, 19])




```python
array_of_floats = np.arange(0,3,0.25)
array_of_floats
```




    array([0.  , 0.25, 0.5 , 0.75, 1.  , 1.25, 1.5 , 1.75, 2.  , 2.25, 2.5 ,
           2.75])



#### Create 2d array


```python
array_2d = np.array([(1,2,3),(4,5,6)])
array_2d
```




    array([[1, 2, 3],
           [4, 5, 6]])



#### Get dimension of an array


```python
array_2d.shape
```




    (2, 3)




```python
rows, columns = array_2d.shape
print(rows)
print(columns)
```

    2
    3


#### Reshape an array


```python
# 2 - rows
# 3 - columns
array_nd = np.arange(6).reshape(2,3)
array_nd
```




    array([[0, 1, 2],
           [3, 4, 5]])



## Print Array

#### 1d Array


```python
a1 = np.arange(5)
print(a1)
```

    [0 1 2 3 4]


#### 2d Array


```python
a2 = np.arange(12).reshape(3,4)
print(a2)
```

    [[ 0  1  2  3]
     [ 4  5  6  7]
     [ 8  9 10 11]]


#### Nd Array


```python
# here it interpretes two arrays of 3x4 dimension
a3 = np.arange(24).reshape(2,3,4)
print(a3)
```

    [[[ 0  1  2  3]
      [ 4  5  6  7]
      [ 8  9 10 11]]
    
     [[12 13 14 15]
      [16 17 18 19]
      [20 21 22 23]]]



```python
print(np.arange(1600))
```

    [   0    1    2 ... 1597 1598 1599]



```python
print(np.arange(1600).reshape(40,40))
```

    [[   0    1    2 ...   37   38   39]
     [  40   41   42 ...   77   78   79]
     [  80   81   82 ...  117  118  119]
     ...
     [1480 1481 1482 ... 1517 1518 1519]
     [1520 1521 1522 ... 1557 1558 1559]
     [1560 1561 1562 ... 1597 1598 1599]]



```python
import sys
np.set_printoptions(threshold=sys.maxsize)
print(np.arange(1600).reshape(40,40))
```

    [[   0    1    2    3    4    5    6    7    8    9   10   11   12   13
        14   15   16   17   18   19   20   21   22   23   24   25   26   27
        28   29   30   31   32   33   34   35   36   37   38   39]
     [  40   41   42   43   44   45   46   47   48   49   50   51   52   53
        54   55   56   57   58   59   60   61   62   63   64   65   66   67
        68   69   70   71   72   73   74   75   76   77   78   79]
     [  80   81   82   83   84   85   86   87   88   89   90   91   92   93
        94   95   96   97   98   99  100  101  102  103  104  105  106  107
       108  109  110  111  112  113  114  115  116  117  118  119]
     [ 120  121  122  123  124  125  126  127  128  129  130  131  132  133
       134  135  136  137  138  139  140  141  142  143  144  145  146  147
       148  149  150  151  152  153  154  155  156  157  158  159]
     [ 160  161  162  163  164  165  166  167  168  169  170  171  172  173
       174  175  176  177  178  179  180  181  182  183  184  185  186  187
       188  189  190  191  192  193  194  195  196  197  198  199]
     [ 200  201  202  203  204  205  206  207  208  209  210  211  212  213
       214  215  216  217  218  219  220  221  222  223  224  225  226  227
       228  229  230  231  232  233  234  235  236  237  238  239]
     [ 240  241  242  243  244  245  246  247  248  249  250  251  252  253
       254  255  256  257  258  259  260  261  262  263  264  265  266  267
       268  269  270  271  272  273  274  275  276  277  278  279]
     [ 280  281  282  283  284  285  286  287  288  289  290  291  292  293
       294  295  296  297  298  299  300  301  302  303  304  305  306  307
       308  309  310  311  312  313  314  315  316  317  318  319]
     [ 320  321  322  323  324  325  326  327  328  329  330  331  332  333
       334  335  336  337  338  339  340  341  342  343  344  345  346  347
       348  349  350  351  352  353  354  355  356  357  358  359]
     [ 360  361  362  363  364  365  366  367  368  369  370  371  372  373
       374  375  376  377  378  379  380  381  382  383  384  385  386  387
       388  389  390  391  392  393  394  395  396  397  398  399]
     [ 400  401  402  403  404  405  406  407  408  409  410  411  412  413
       414  415  416  417  418  419  420  421  422  423  424  425  426  427
       428  429  430  431  432  433  434  435  436  437  438  439]
     [ 440  441  442  443  444  445  446  447  448  449  450  451  452  453
       454  455  456  457  458  459  460  461  462  463  464  465  466  467
       468  469  470  471  472  473  474  475  476  477  478  479]
     [ 480  481  482  483  484  485  486  487  488  489  490  491  492  493
       494  495  496  497  498  499  500  501  502  503  504  505  506  507
       508  509  510  511  512  513  514  515  516  517  518  519]
     [ 520  521  522  523  524  525  526  527  528  529  530  531  532  533
       534  535  536  537  538  539  540  541  542  543  544  545  546  547
       548  549  550  551  552  553  554  555  556  557  558  559]
     [ 560  561  562  563  564  565  566  567  568  569  570  571  572  573
       574  575  576  577  578  579  580  581  582  583  584  585  586  587
       588  589  590  591  592  593  594  595  596  597  598  599]
     [ 600  601  602  603  604  605  606  607  608  609  610  611  612  613
       614  615  616  617  618  619  620  621  622  623  624  625  626  627
       628  629  630  631  632  633  634  635  636  637  638  639]
     [ 640  641  642  643  644  645  646  647  648  649  650  651  652  653
       654  655  656  657  658  659  660  661  662  663  664  665  666  667
       668  669  670  671  672  673  674  675  676  677  678  679]
     [ 680  681  682  683  684  685  686  687  688  689  690  691  692  693
       694  695  696  697  698  699  700  701  702  703  704  705  706  707
       708  709  710  711  712  713  714  715  716  717  718  719]
     [ 720  721  722  723  724  725  726  727  728  729  730  731  732  733
       734  735  736  737  738  739  740  741  742  743  744  745  746  747
       748  749  750  751  752  753  754  755  756  757  758  759]
     [ 760  761  762  763  764  765  766  767  768  769  770  771  772  773
       774  775  776  777  778  779  780  781  782  783  784  785  786  787
       788  789  790  791  792  793  794  795  796  797  798  799]
     [ 800  801  802  803  804  805  806  807  808  809  810  811  812  813
       814  815  816  817  818  819  820  821  822  823  824  825  826  827
       828  829  830  831  832  833  834  835  836  837  838  839]
     [ 840  841  842  843  844  845  846  847  848  849  850  851  852  853
       854  855  856  857  858  859  860  861  862  863  864  865  866  867
       868  869  870  871  872  873  874  875  876  877  878  879]
     [ 880  881  882  883  884  885  886  887  888  889  890  891  892  893
       894  895  896  897  898  899  900  901  902  903  904  905  906  907
       908  909  910  911  912  913  914  915  916  917  918  919]
     [ 920  921  922  923  924  925  926  927  928  929  930  931  932  933
       934  935  936  937  938  939  940  941  942  943  944  945  946  947
       948  949  950  951  952  953  954  955  956  957  958  959]
     [ 960  961  962  963  964  965  966  967  968  969  970  971  972  973
       974  975  976  977  978  979  980  981  982  983  984  985  986  987
       988  989  990  991  992  993  994  995  996  997  998  999]
     [1000 1001 1002 1003 1004 1005 1006 1007 1008 1009 1010 1011 1012 1013
      1014 1015 1016 1017 1018 1019 1020 1021 1022 1023 1024 1025 1026 1027
      1028 1029 1030 1031 1032 1033 1034 1035 1036 1037 1038 1039]
     [1040 1041 1042 1043 1044 1045 1046 1047 1048 1049 1050 1051 1052 1053
      1054 1055 1056 1057 1058 1059 1060 1061 1062 1063 1064 1065 1066 1067
      1068 1069 1070 1071 1072 1073 1074 1075 1076 1077 1078 1079]
     [1080 1081 1082 1083 1084 1085 1086 1087 1088 1089 1090 1091 1092 1093
      1094 1095 1096 1097 1098 1099 1100 1101 1102 1103 1104 1105 1106 1107
      1108 1109 1110 1111 1112 1113 1114 1115 1116 1117 1118 1119]
     [1120 1121 1122 1123 1124 1125 1126 1127 1128 1129 1130 1131 1132 1133
      1134 1135 1136 1137 1138 1139 1140 1141 1142 1143 1144 1145 1146 1147
      1148 1149 1150 1151 1152 1153 1154 1155 1156 1157 1158 1159]
     [1160 1161 1162 1163 1164 1165 1166 1167 1168 1169 1170 1171 1172 1173
      1174 1175 1176 1177 1178 1179 1180 1181 1182 1183 1184 1185 1186 1187
      1188 1189 1190 1191 1192 1193 1194 1195 1196 1197 1198 1199]
     [1200 1201 1202 1203 1204 1205 1206 1207 1208 1209 1210 1211 1212 1213
      1214 1215 1216 1217 1218 1219 1220 1221 1222 1223 1224 1225 1226 1227
      1228 1229 1230 1231 1232 1233 1234 1235 1236 1237 1238 1239]
     [1240 1241 1242 1243 1244 1245 1246 1247 1248 1249 1250 1251 1252 1253
      1254 1255 1256 1257 1258 1259 1260 1261 1262 1263 1264 1265 1266 1267
      1268 1269 1270 1271 1272 1273 1274 1275 1276 1277 1278 1279]
     [1280 1281 1282 1283 1284 1285 1286 1287 1288 1289 1290 1291 1292 1293
      1294 1295 1296 1297 1298 1299 1300 1301 1302 1303 1304 1305 1306 1307
      1308 1309 1310 1311 1312 1313 1314 1315 1316 1317 1318 1319]
     [1320 1321 1322 1323 1324 1325 1326 1327 1328 1329 1330 1331 1332 1333
      1334 1335 1336 1337 1338 1339 1340 1341 1342 1343 1344 1345 1346 1347
      1348 1349 1350 1351 1352 1353 1354 1355 1356 1357 1358 1359]
     [1360 1361 1362 1363 1364 1365 1366 1367 1368 1369 1370 1371 1372 1373
      1374 1375 1376 1377 1378 1379 1380 1381 1382 1383 1384 1385 1386 1387
      1388 1389 1390 1391 1392 1393 1394 1395 1396 1397 1398 1399]
     [1400 1401 1402 1403 1404 1405 1406 1407 1408 1409 1410 1411 1412 1413
      1414 1415 1416 1417 1418 1419 1420 1421 1422 1423 1424 1425 1426 1427
      1428 1429 1430 1431 1432 1433 1434 1435 1436 1437 1438 1439]
     [1440 1441 1442 1443 1444 1445 1446 1447 1448 1449 1450 1451 1452 1453
      1454 1455 1456 1457 1458 1459 1460 1461 1462 1463 1464 1465 1466 1467
      1468 1469 1470 1471 1472 1473 1474 1475 1476 1477 1478 1479]
     [1480 1481 1482 1483 1484 1485 1486 1487 1488 1489 1490 1491 1492 1493
      1494 1495 1496 1497 1498 1499 1500 1501 1502 1503 1504 1505 1506 1507
      1508 1509 1510 1511 1512 1513 1514 1515 1516 1517 1518 1519]
     [1520 1521 1522 1523 1524 1525 1526 1527 1528 1529 1530 1531 1532 1533
      1534 1535 1536 1537 1538 1539 1540 1541 1542 1543 1544 1545 1546 1547
      1548 1549 1550 1551 1552 1553 1554 1555 1556 1557 1558 1559]
     [1560 1561 1562 1563 1564 1565 1566 1567 1568 1569 1570 1571 1572 1573
      1574 1575 1576 1577 1578 1579 1580 1581 1582 1583 1584 1585 1586 1587
      1588 1589 1590 1591 1592 1593 1594 1595 1596 1597 1598 1599]]



```python
#default is 1000
np.set_printoptions(threshold=1000)
print(np.arange(1600).reshape(40,40))
```

    [[   0    1    2 ...   37   38   39]
     [  40   41   42 ...   77   78   79]
     [  80   81   82 ...  117  118  119]
     ...
     [1480 1481 1482 ... 1517 1518 1519]
     [1520 1521 1522 ... 1557 1558 1559]
     [1560 1561 1562 ... 1597 1598 1599]]


## Array Operations


```python
a = np.array([10,10,10])
b = np.array([5,5,5])
```

#### Addition


```python
a+b
```




    array([15, 15, 15])



#### Subtraction


```python
a-b
```




    array([5, 5, 5])



#### Multiplication


```python
a*b
```




    array([50, 50, 50])



#### Division


```python
a/b
```




    array([2., 2., 2.])



#### Modulus


```python
a%3
```




    array([1, 1, 1])



#### Conditional Operators


```python
a<15
```




    array([ True,  True,  True])




```python
b>15
```




    array([False, False, False])



#### Nd Multiplication


```python
A = np.array([(1,2),(3,4)])
B = np.array([(4,3),(2,1)])

print('A:\n',A)
print('B:\n',B)
```

    A:
     [[1 2]
     [3 4]]
    B:
     [[4 3]
     [2 1]]



```python
A * B
```




    array([[4, 6],
           [6, 4]])



#### Dot Mulitplication


```python
A.dot(B)
```




    array([[ 8,  5],
           [20, 13]])




```python
np.dot(A,B)
```




    array([[ 8,  5],
           [20, 13]])



#### Self Assignment Operators


```python
a *= 2
a
```




    array([20, 20, 20])




```python
b += a
b
```




    array([25, 25, 25])



#### Basic Functions


```python
ages = np.array([10,8,7,12])
```


```python
ages.sum()
```




    37




```python
ages.min()
```




    7




```python
ages.max()
```




    12




```python
numbers = np.arange(12).reshape(3,4)
numbers
```




    array([[ 0,  1,  2,  3],
           [ 4,  5,  6,  7],
           [ 8,  9, 10, 11]])




```python
# here axis=0 means columns
numbers.sum(axis=0)
```




    array([12, 15, 18, 21])




```python
# here axis=1 means rows
numbers.sum(axis=1)
```




    array([ 6, 22, 38])




```python
# here axis=0 means columns
numbers.max(axis=0)
```




    array([ 8,  9, 10, 11])




```python
# here axis=1 means rows
numbers.min(axis=1)
```




    array([0, 4, 8])



## Universal Functions

### Mathematical Functions


```python
angles = np.array([0,30,45,60,90])
```


```python
angle_radians = angles * np.pi/180
angle_radians
```




    array([0.        , 0.52359878, 0.78539816, 1.04719755, 1.57079633])




```python
print(np.sin(angle_radians))
```

    [0.         0.5        0.70710678 0.8660254  1.        ]



```python
angle_radians = np.radians(angles)
angle_radians
```




    array([0.        , 0.52359878, 0.78539816, 1.04719755, 1.57079633])




```python
print(np.cos(angle_radians))
```

    [1.00000000e+00 8.66025404e-01 7.07106781e-01 5.00000000e-01
     6.12323400e-17]



```python
print(np.tan(angle_radians))
```

    [0.00000000e+00 5.77350269e-01 1.00000000e+00 1.73205081e+00
     1.63312394e+16]



```python
sin = np.sin(angle_radians)
inv = np.arcsin(sin)
print(inv)
```

    [0.         0.52359878 0.78539816 1.04719755 1.57079633]



```python
cos = np.cos(angle_radians)
inv = np.arccos(cos)
print(inv)
```

    [0.         0.52359878 0.78539816 1.04719755 1.57079633]



```python
np.degrees(angle_radians)
```




    array([ 0., 30., 45., 60., 90.])



### Statistical Functions


```python
marks = np.array([31,53,97,86,12,76,74,54,64,60,66,87,54,73,65])
print(marks)
```

    [31 53 97 86 12 76 74 54 64 60 66 87 54 73 65]



```python
np.median(marks)
```




    65.0




```python
mean     = np.mean(marks)
median     = np.median(marks)
sd       = np.std(marks)
variance = np.var(marks)

print("Mean = %i"%mean)
print("Median = %i"%median)
print("Standard Deviation = %i"%sd)
print("Variance = %i"%variance)
```

    Mean = 63
    Median = 65
    Standard Deviation = 20
    Variance = 437


## Indexing and Slicing


```python
a = np.arange(10)**2
a
```




    array([ 0,  1,  4,  9, 16, 25, 36, 49, 64, 81])




```python
# first index is 0
a[3]
```




    9




```python
# last index is -1
a[-3]
```




    49




```python
# index 2 is included and index 6 is excluded
a[2:6]
```




    array([ 4,  9, 16, 25])




```python
a[2:]
```




    array([ 4,  9, 16, 25, 36, 49, 64, 81])




```python
a[:6]
```




    array([ 0,  1,  4,  9, 16, 25])




```python
a[:-2]
```




    array([ 0,  1,  4,  9, 16, 25, 36, 49])




```python
a[-2:]
```




    array([64, 81])




```python
# start: beginning
# end: 7
# step: 2
a[:7:2]
```




    array([ 0,  4, 16, 36])




```python
# start: beginning
# end: end
# step: -1

#Reverse of numpy array
a[::-1]
```




    array([81, 64, 49, 36, 25, 16,  9,  4,  1,  0])




```python
students = np.array([['Amit','Arya','Jon','Cersie'],[65,87,43,83],[98,43,76,57]])
students
```




    array([['Amit', 'Arya', 'Jon', 'Cersie'],
           ['65', '87', '43', '83'],
           ['98', '43', '76', '57']], dtype='<U6')




```python
students[0]
```




    array(['Amit', 'Arya', 'Jon', 'Cersie'], dtype='<U6')




```python
students[1]
```




    array(['65', '87', '43', '83'], dtype='<U6')




```python
students[0,1]
```




    'Arya'




```python
# Intersection of 1st and 2nd row & 3nd and 4rd column
students[0:2,2:4]
```




    array([['Jon', 'Cersie'],
           ['43', '83']], dtype='<U6')




```python
# all rows of 1st column
# here 2 is excluded
students[:,1:2]
```




    array([['Arya'],
           ['87'],
           ['43']], dtype='<U6')




```python
# all rows of 1st and 2nd column
# here 3 is excluded
students[:,1:3]
```




    array([['Arya', 'Jon'],
           ['87', '43'],
           ['43', '76']], dtype='<U6')




```python
#all columns of second last row
students[-2,:]
```




    array(['65', '87', '43', '83'], dtype='<U6')




```python
# all columns of first row
students[0,...]
```




    array(['Amit', 'Arya', 'Jon', 'Cersie'], dtype='<U6')




```python
# all rows of 2nd column
students[...,1]
```




    array(['Arya', '87', '43'], dtype='<U6')



## Iterating over Arrays


```python
a = np.arange(11)**2
print(a)
```

    [  0   1   4   9  16  25  36  49  64  81 100]



```python
for i in a:
    print(i**(1/2))
```

    0.0
    1.0
    2.0
    3.0
    4.0
    5.0
    6.0
    7.0
    8.0
    9.0
    10.0



```python
students = np.array([['Amit','Arya','Jon','Cersie'],
                     [65,87,43,83],
                     [98,43,76,57]])
for i in students:
    print('i = ',i)
```

    i =  ['Amit' 'Arya' 'Jon' 'Cersie']
    i =  ['65' '87' '43' '83']
    i =  ['98' '43' '76' '57']


#### Iterate using `flatten()`


```python
for i in students.flatten():
    print(i)
```

    Amit
    Arya
    Jon
    Cersie
    65
    87
    43
    83
    98
    43
    76
    57



```python
# order = 'F' means column flattening - elements in column appear together
for i in students.flatten(order='F'):
    print(i)
```

    Amit
    65
    98
    Arya
    87
    43
    Jon
    43
    76
    Cersie
    83
    57



```python
a = np.arange(12).reshape(3,4)
print(a)
```

    [[ 0  1  2  3]
     [ 4  5  6  7]
     [ 8  9 10 11]]


#### Iterate using `nditer()`


```python
# nditer - iterate elements of one by one row
for i in np.nditer(a):
    print(i)
```

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11



```python
# nditer - order = 'F' means iterate elements of one by one column
for i in np.nditer(a,order='F'):
    print(i)
```

    0
    4
    8
    1
    5
    9
    2
    6
    10
    3
    7
    11


##### flatten vs nditer
**flatten** actually returns a result array, **nditer** allows to iterate over elements

##### `external_loop` flag in `nditer`

`external_loop` returns an array.


```python
for i in np.nditer(a,order='F',flags=['external_loop']):
    print(i)
```

    [0 4 8]
    [1 5 9]
    [ 2  6 10]
    [ 3  7 11]


##### `readwrite` op_flag in `nditer`


```python
import traceback
a = np.arange(12).reshape(3,4)
for i in np.nditer(a):
    try:
     # here arr is read only by default so it will throw error
     i[...] = i * i
    except ValueError:
        traceback.print_exc()
        break
```

    Traceback (most recent call last):
      File "<ipython-input-87-8c1815e8c528>", line 6, in <module>
        i[...] = i * i
    ValueError: assignment destination is read-only



```python
a = np.arange(12).reshape(3,4)
for arr in np.nditer(a,op_flags = ['readwrite']):
    arr[...] = arr * arr
print(a)
```

    [[  0   1   4   9]
     [ 16  25  36  49]
     [ 64  81 100 121]]


## Reshaping Arrays


```python
cities = np.array([['Rajkot','Ahmedabad','Mumbai'],['Chennai','Kolkata','Pune']])
cities
```




    array([['Rajkot', 'Ahmedabad', 'Mumbai'],
           ['Chennai', 'Kolkata', 'Pune']], dtype='<U9')




```python
cities.shape
```




    (2, 3)



#### Flattening to a 1d array


```python
cities.ravel()
```




    array(['Rajkot', 'Ahmedabad', 'Mumbai', 'Chennai', 'Kolkata', 'Pune'],
          dtype='<U9')



#### Transpose of an array


```python
cities.T
```




    array([['Rajkot', 'Chennai'],
           ['Ahmedabad', 'Kolkata'],
           ['Mumbai', 'Pune']], dtype='<U9')




```python
cities.T.ravel()
#element in differnt orders
```




    array(['Rajkot', 'Chennai', 'Ahmedabad', 'Kolkata', 'Mumbai', 'Pune'],
          dtype='<U9')



#### Reshape an Array


```python
print(cities)
cities.reshape(3,2)
```

    [['Rajkot' 'Ahmedabad' 'Mumbai']
     ['Chennai' 'Kolkata' 'Pune']]





    array([['Rajkot', 'Ahmedabad'],
           ['Mumbai', 'Chennai'],
           ['Kolkata', 'Pune']], dtype='<U9')




```python
np.arange(12).reshape(3,4)
```




    array([[ 0,  1,  2,  3],
           [ 4,  5,  6,  7],
           [ 8,  9, 10, 11]])




```python
np.arange(12).reshape(4,3)
```




    array([[ 0,  1,  2],
           [ 3,  4,  5],
           [ 6,  7,  8],
           [ 9, 10, 11]])




```python
import traceback
try:
    np.arange(15).reshape(4,4)
except ValueError:
    traceback.print_exc()
```

    Traceback (most recent call last):
      File "<ipython-input-97-df19d88243b7>", line 3, in <module>
        np.arange(15).reshape(4,4)
    ValueError: cannot reshape array of size 15 into shape (4,4)



```python
# here negative number means we don't know number of rows
# 3 columns
cities.reshape(-1,3)
```




    array([['Rajkot', 'Ahmedabad', 'Mumbai'],
           ['Chennai', 'Kolkata', 'Pune']], dtype='<U9')




```python
# here negative number means we don't know number of columns
# 3 rows
cities.reshape(3,-1)
```




    array([['Rajkot', 'Ahmedabad'],
           ['Mumbai', 'Chennai'],
           ['Kolkata', 'Pune']], dtype='<U9')




```python
import traceback
try:
    cities.reshape(4,-1)
except ValueError:
    traceback.print_exc()
```

    Traceback (most recent call last):
      File "<ipython-input-100-b62991f143dc>", line 3, in <module>
        cities.reshape(4,-1)
    ValueError: cannot reshape array of size 6 into shape (4,newaxis)


## Splitting an Array


```python
a = np.arange(9)
```


```python
a
```




    array([0, 1, 2, 3, 4, 5, 6, 7, 8])



#### Split in equal size sub-array


```python
np.split(a,3)
```




    [array([0, 1, 2]), array([3, 4, 5]), array([6, 7, 8])]



#### Split the array at positions


```python
np.split(a,[4,7])
```




    [array([0, 1, 2, 3]), array([4, 5, 6]), array([7, 8])]



#### Split array horizontally


```python
a = np.arange(8).reshape(2,4)
print(a)
```

    [[0 1 2 3]
     [4 5 6 7]]



```python
a1, a2 = np.hsplit(a,2)
print('a1 =\n',a1)
print('a2 =\n',a2)
```

    a1 =
     [[0 1]
     [4 5]]
    a2 =
     [[2 3]
     [6 7]]



```python
np.hsplit(a,4)
```




    [array([[0],
            [4]]), array([[1],
            [5]]), array([[2],
            [6]]), array([[3],
            [7]])]



#### Split array vertically


```python
a = np.arange(8).reshape(2,4)
a
```




    array([[0, 1, 2, 3],
           [4, 5, 6, 7]])




```python
a1,a2 = np.vsplit(a,2)
print('a1 =',a1)
print('a2 =',a2)
```

    a1 = [[0 1 2 3]]
    a2 = [[4 5 6 7]]


## Shallow Copies

NumPy has `view()` method which is used to create an array object that looks at the same data of the original array. Change in dimensions of the new array doesn’t change dimensions of the original, but change in data also change data in origional.


```python
fruits = np.array(['Apple','Mango','Grapes','Strawberry'])
```


```python
basket_1 = fruits.view()
basket_2 = fruits.view()
```


```python
print(basket_1)
print(basket_2)
```

    ['Apple' 'Mango' 'Grapes' 'Strawberry']
    ['Apple' 'Mango' 'Grapes' 'Strawberry']



```python
##Ids for the arrays are different
print(id(fruits))
print(id(basket_1))
print(id(basket_2))
```

    4505422864
    4505438528
    4505372832



```python
basket_1 is fruits
```




    False




```python
basket_1.base is fruits
```




    True




```python
#Also change data of an origional array
basket_2[0] = 'Banana'
print('Fruits:\n',fruits)
print('Basket 1:\n',basket_1)
print('Basket 2:\n',basket_2)
```

    Fruits:
     ['Banana' 'Mango' 'Grapes' 'Strawberry']
    Basket 1:
     ['Banana' 'Mango' 'Grapes' 'Strawberry']
    Basket 2:
     ['Banana' 'Mango' 'Grapes' 'Strawberry']



```python
basket_2 is basket_1
```




    False




```python
#Doesn't change dimension of an origional array
basket_2.shape = 2,2
print('Fruits:\n',fruits)
print('Basket 1:\n',basket_1)
print('Basket 2:\n',basket_2)
```

    Fruits:
     ['Banana' 'Mango' 'Grapes' 'Strawberry']
    Basket 1:
     ['Banana' 'Mango' 'Grapes' 'Strawberry']
    Basket 2:
     [['Banana' 'Mango']
     ['Grapes' 'Strawberry']]


## Deep Copies

The `copy()` function creates a deep copy. It is a complete copy of the array and its data, and doesn’t share with the original array.


```python
fruits = np.array(['Apple','Mango','Grapes','Strawberry'])
basket_1 = fruits.copy()
basket_2 = fruits.copy()
print('Fruits:\n',fruits)
print('Basket 1:\n',basket_1)
print('Basket 2:\n',basket_2)
```

    Fruits:
     ['Apple' 'Mango' 'Grapes' 'Strawberry']
    Basket 1:
     ['Apple' 'Mango' 'Grapes' 'Strawberry']
    Basket 2:
     ['Apple' 'Mango' 'Grapes' 'Strawberry']



```python
#Doesn't change data of an origional array
basket_1[0]='Banana'
print('Fruits:\n',fruits)
print('Basket 1:\n',basket_1)
print('Basket 2:\n',basket_2)
```

    Fruits:
     ['Apple' 'Mango' 'Grapes' 'Strawberry']
    Basket 1:
     ['Banana' 'Mango' 'Grapes' 'Strawberry']
    Basket 2:
     ['Apple' 'Mango' 'Grapes' 'Strawberry']



```python
#Doesn't change dimension of an origional array
basket_2.shape = 2,2
print('Fruits:\n',fruits)
print('Basket 1:\n',basket_1)
print('Basket 2:\n',basket_2)
```

    Fruits:
     ['Apple' 'Mango' 'Grapes' 'Strawberry']
    Basket 1:
     ['Banana' 'Mango' 'Grapes' 'Strawberry']
    Basket 2:
     [['Apple' 'Mango']
     ['Grapes' 'Strawberry']]

