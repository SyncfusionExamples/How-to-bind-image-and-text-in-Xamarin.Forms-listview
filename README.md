# How to bind image and text in the listview
This example demonstrates how to display the image and text in the listview by binding them.

## Sample

```xaml
<Grid Margin="0">
    <syncfusion:SfListView x:Name="listView"
                            ItemSize="70"
                            ItemsSource="{Binding ContactsInfo}">
        <syncfusion:SfListView.ItemTemplate>
            <DataTemplate>
                <ViewCell>
                    <ViewCell.View>
                        <Grid x:Name="grid" RowSpacing="0">
                            <Grid.RowDefinitions>
                                <RowDefinition Height="*" />
                                <RowDefinition Height="1" />
                            </Grid.RowDefinitions>
                            <Grid RowSpacing="0">
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="70" />
                                    <ColumnDefinition Width="*" />
                                    <ColumnDefinition Width="Auto" />
                                </Grid.ColumnDefinitions>

                                <Image Source="{Binding ContactImage}"
                                        VerticalOptions="Center"
                                        HorizontalOptions="Center"
                                        HeightRequest="50" WidthRequest="50"/>

                                <Grid Grid.Column="1"
                                        RowSpacing="1"
                                        Padding="10,0,0,0"
                                        VerticalOptions="Center">
                                    <Grid.RowDefinitions>
                                        <RowDefinition Height="*" />
                                        <RowDefinition Height="*" />
                                    </Grid.RowDefinitions>

                                    <Label LineBreakMode="NoWrap"
                                            TextColor="#474747"
                                            Text="{Binding ContactName}">
                                        <Label.FontSize>
                                            <OnPlatform x:TypeArguments="x:Double">
                                                <On  Platform="Android,iOS">
                                                    <OnIdiom x:TypeArguments="x:Double" Phone="16" Tablet="18" />
                                                </On>
                                                <On  Platform="UWP">
                                                    <OnIdiom x:TypeArguments="x:Double" Phone="18" Tablet="20" Desktop="20" />
                                                </On>
                                                <On  Platform="macOS" Value="18"/>
                                            </OnPlatform>
                                        </Label.FontSize>
                                    </Label>
                                    <Label Grid.Row="1"
                                            Grid.Column="0"
                                            TextColor="#474747"
                                            LineBreakMode="NoWrap"
                                            Text="{Binding ContactNumber}">
                                        <Label.FontSize>
                                            <OnPlatform x:TypeArguments="x:Double">
                                                <On  Platform="Android,iOS">
                                                <OnIdiom x:TypeArguments="x:Double" Phone="12" Tablet="14" />
                                                </On>
                                                <On  Platform="UWP">
                                                    <OnIdiom x:TypeArguments="x:Double" Phone="12" Tablet="12" Desktop="12" />
                                                </On>
                                                <On  Platform="macOS" Value="14"/>
                                            </OnPlatform>
                                        </Label.FontSize>
                                    </Label>
                                </Grid>
                                <Grid Grid.Row="0"
                                        Grid.Column="2"
                                        RowSpacing="0"
                                        HorizontalOptions="End" VerticalOptions="Start">
                                    <Grid.Padding>
                                        <OnPlatform x:TypeArguments="Thickness">
                                            <On  Platform="iOS">
                                                <OnIdiom x:TypeArguments="Thickness" Phone="0,10,10,0" Tablet="0,10,10,0"  />
                                            </On>
                                            <On  Platform="Android,UWP">
                                                <OnIdiom x:TypeArguments="Thickness" Phone="0,10,10,0" Tablet="0,10,10,0" Desktop="0,10,10,0" />
                                            </On>
                                            <On  Platform="macOS" Value="0,10,15,0"/>
                                        </OnPlatform>
                                    </Grid.Padding>
                                    <Label LineBreakMode="NoWrap"
                                            TextColor="#474747"
                                            Text="{Binding ContactType}">
                                        <Label.FontSize>
                                            <OnPlatform x:TypeArguments="x:Double">
                                                <On  Platform="Android,iOS">
                                                    <OnIdiom x:TypeArguments="x:Double" Phone="10" Tablet="12" />
                                                </On>
                                                <On  Platform="UWP">
                                                    <OnIdiom x:TypeArguments="x:Double" Phone="10" Tablet="11" Desktop="11" />
                                                </On>
                                                <On  Platform="macOS" Value="12"/>
                                            </OnPlatform>
                                        </Label.FontSize>
                                    </Label>
                                </Grid>
                            </Grid>
                            <StackLayout Grid.Row="1" BackgroundColor="#E4E4E4" HeightRequest="1"/>
                        </Grid>
                    </ViewCell.View>
                </ViewCell>
            </DataTemplate>
        </syncfusion:SfListView.ItemTemplate>
    </syncfusion:SfListView>
</Grid>
```

See [How to bind image and text in the listview](https://www.syncfusion.com/kb/9636/how-to-bind-image-and-text-in-the-listview) for more details.

## <a name="requirements-to-run-the-demo"></a>Requirements to run the demo ##

* [Visual Studio 2017](https://visualstudio.microsoft.com/downloads/) or [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/).
* Xamarin add-ons for Visual Studio (available via the Visual Studio installer).

## <a name="troubleshooting"></a>Troubleshooting ##
### Path too long exception
If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.
