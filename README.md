# GIS-
拼凑版裁切程序
void CMyView::OnFileOpen() 
{
	// TODO: Add your command handler code here
	/*CFileDialog fDlg(true);//ture 读     false 写*/
	FILE *fp;
    /*CString fileName=("");
	if(fDlg.DoModal()==IDOK)
		fileName=fDlg.GetPathName();
	fp= fopen("C:\\Users\\9.6\\Desktop\\MFCApplication2\\chinaBoundaryL.mif","r" );//r 读， rb 读二进制  C:\\clipData.txt
	    CPoint pt;
		map = new CGeoMap();
		CGeoLayer * layer = new CGeoLayer();
		int c = 1000000;
		while (!feof(fp))
		{
			fscanf(fp, "%s", s_dk);
			int x, y, minx, miny, maxx, maxy;

			if (strcmp(s_dk, "Bounds") == 0)
			{
				float a;
				fscanf(fp, "%f", &a);
				a = a * c;
				minx = a;
				fscanf(fp, "%f", &a);
				a = a * c;
				maxy = a;
				fscanf(fp, "%f", &a);
				a = a * c;
				maxx = a;
				fscanf(fp, "%f", &a);
				a = a * c;
				miny = a;
				map->wcRect = CRect(minx, miny, maxx, maxy);
				map->clipRect = CRect(minx*6, miny/6, maxx/6, maxy*6);
			}

			if (strcmp(s_dk, "Pline") == 0 || strcmp(s_dk, "Line") == 0)/*即扫描到线的定义时，进入IF*/
			{
				if (strcmp(s_dk, "Line") == 0)
				{
					m_count = 2;
				}
				else fscanf(fp, "%d", &m_count);
		CGeoPolyline *poly = new CGeoPolyline();/*根据文件书写模式来定义的读数据模式*/
				for (int i = 0; i < m_count; i++)
				{
					float a, b;
					fscanf(fp, "%f%f", &a, &b);
					a = a * c;
					b = b * c;
					pt.x = a;
					pt.y = b;
					poly->addPoint(pt);
				}
				layer->addPolyline(poly);
			}
			if (layer == NULL)
			{
				free(layer);
			}
		}
		CGeoPolyline *poly = new CGeoPolyline();
		poly->clipPolyline(map->clipRect);

		map->addLayer(layer);/*一个文件中只有一个图层咯这个意思是*/
		fclose(fp);
		map->clipMap(map->clipRect);
	this->isOK = true;
	this->load = true;

	Invalidate();//激活重绘
}


/////////////////////////////

void CGeoPolyline::clipPolyline(CRect clipRect1)
{
    int size=pts.GetSize();
    CPoint pp;
    for(int i=0;i<size;i++)
	{
	  
	pp=pts[i];
if(裁切方框的条件）
clippts.Add(pp);
		  
}
