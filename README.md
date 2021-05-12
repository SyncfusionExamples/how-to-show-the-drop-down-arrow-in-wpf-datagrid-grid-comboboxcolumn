# How to show the DropDownArrow in WPF DataGrid (SfDataGrid) GridComboBoxColumn 

## About the sample

This example illustrates how to show the DropDownArrow in WPF DataGrid (SfDataGrid) GridComboBoxColumn.

In [WPF DataGrid](https://www.syncfusion.com/wpf-controls/datagrid) (SfDataGrid), the drop-down arrow for [GridComboBoxColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridComboBoxColumn.html) will be shown only in the edit mode. You can differentiate the combo box column from other columns by showing the drop-down arrow in the display mode by using CellStyle property of the corresponding column.

```Xaml
<Window.Resources>
    <Style x:Key="comboBoxCellStyle" TargetType="syncfusion:GridCell">
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="syncfusion:GridCell">
                    <Grid SnapsToDevicePixels="True">
                        <Border Background="{TemplateBinding Background}"
                                BorderBrush="{TemplateBinding BorderBrush}"
                                BorderThickness="{TemplateBinding BorderThickness}"
                                SnapsToDevicePixels="True">
                            <Grid>
                                <ContentPresenter Margin="{TemplateBinding Padding}" />
                                <Path Width="5.3"
                                      Height="4.2"
                                      Margin="0,0,7,0"
                                      HorizontalAlignment="Right"
                                      VerticalAlignment="Center"
                                      Data="F1M0,0L2.667,2.66665 5.3334,0 5.3334,-1.78168 2.6667,0.88501 0,-1.78168 0,0z"
                                      Fill="Gray"
                                      Stretch="Uniform" />
                            </Grid>
                        </Border>
                    </Grid>
                </ControlTemplate>
            </Setter.Value>
        </Setter>

    </Style>
</Window.Resources>


<Grid>
    <syncfusion:SfDataGrid Name="dataGrid"
                           Margin="20"
                           AutoGenerateColumns="False"
                           AllowEditing="True"
                           ColumnSizer="Auto"
                           ItemsSource="{Binding Employees}">
        <syncfusion:SfDataGrid.Columns>
            <syncfusion:GridComboBoxColumn MappingName="Country" ItemsSource="{Binding Countries}" CellStyle="{StaticResource comboBoxCellStyle}">
            </syncfusion:GridComboBoxColumn>
        </syncfusion:SfDataGrid.Columns>
    </syncfusion:SfDataGrid>
</Grid>

```

![GridComboBoxColumn DropDown](GridComboBoxColumn_DropDown.png)
