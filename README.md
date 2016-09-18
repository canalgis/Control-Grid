# Control Grid
Utilización del control Grid, muestra el ordenamiento de los controles en una aplicación de un restauran.


<Page
    x:Class="App14.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:App14"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}" HorizontalAlignment="Center">
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="*"/>
        </Grid.ColumnDefinitions>
        <!--<StackPanel HorizontalAlignment="Left" Height="620" Margin="10,10,0,0" VerticalAlignment="Top" Width="340" BorderThickness="20,0,0,0" Grid.Row="12" Grid.Column="6">-->

        <Grid.RowDefinitions>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>




        <ComboBox x:Name="comboBox" HorizontalAlignment="Stretch" VerticalAlignment="Top" Margin="41,72,39,0" SelectionChanged="comboBox_SelectionChanged" Grid.Row="0" Grid.Column="0" Height="29">
            <ComboBoxItem Content="1"/>
            <ComboBoxItem Content="2"/>
            <ComboBoxItem Content="3"/>
            <ComboBoxItem Content="4" IsSelected="True"/>

        </ComboBox>
        <TextBlock Grid.Column="1"
            x:Name="PROPINA" TextWrapping="Wrap" Text="PROPINA %" HorizontalAlignment="Left" RenderTransformOrigin="-0.269,0.5" Margin="32,30,0,0" Width="100" Height="20" VerticalAlignment="Top" />
        <ComboBox x:Name="comboBox1" HorizontalAlignment="Stretch" VerticalAlignment="Top" Margin="33,72,11,0" Grid.Column="1" SelectionChanged="comboBox1_SelectionChanged" Height="29">
            <ComboBoxItem Content="10" />
            <ComboBoxItem Content="15" IsSelected="True"/>
        </ComboBox>
        <TextBlock x:Name="textBlock1" TextWrapping="Wrap" Text="MONTO" Margin="59,39.667,41,0" RenderTransformOrigin="0.553,0.484" Grid.Row="1" Height="20" VerticalAlignment="Top"/>
        <TextBox x:Name="textBoxMonto" TextWrapping="Wrap" Text="" HorizontalAlignment="Left" Width="100" Margin="39,83.667,0,0" Grid.Row="1" Height="29" VerticalAlignment="Top"/>
        <TextBlock x:Name="textBlock2" TextWrapping="Wrap" Text="PAGO " Margin="53,35.667,48,0" Grid.Column="1" Grid.Row="1" Height="20" VerticalAlignment="Top"/>
        <TextBox x:Name="textBoxPago" TextWrapping="Wrap" Text="" Margin="35,83.667,45,0" TextChanged="textBoxPago_TextChanged" Grid.Row="1" Grid.Column="1" Height="32" VerticalAlignment="Top"/>
        <TextBlock x:Name="ComboBoxResultTextBlock" TextWrapping="Wrap" Text="TextBlock" Margin="0,0,244,0"/>
        <Button x:Name="buttonPagar" Content="PAGAR" HorizontalAlignment="Center" VerticalAlignment="Top" Margin="44,59.333,36,0" Click="buttonPagar_Click" Grid.Row="2" Width="100" Height="29"/>


        <!-- </StackPanel>-->
        <TextBlock x:Name="textBlock" Margin="51,30,0,0" TextWrapping="Wrap" Text="CLIENTES" VerticalAlignment="Top" HorizontalAlignment="Left" Width="63"/>
    </Grid>
</Page>








using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Runtime.InteropServices.WindowsRuntime;
using Windows.Foundation;
using Windows.Foundation.Collections;
using Windows.UI.Xaml;
using Windows.UI.Xaml.Controls;
using Windows.UI.Xaml.Controls.Primitives;
using Windows.UI.Xaml.Data;
using Windows.UI.Xaml.Input;
using Windows.UI.Xaml.Media;
using Windows.UI.Xaml.Navigation;

// The Blank Page item template is documented at http://go.microsoft.com/fwlink/?LinkId=402352&clcid=0x409

namespace App14
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();
        }

        private void CLIENTES_SelectionChanged(object sender, RoutedEventArgs e)
        {

        }

        private void comboBox_SelectionChanged(object sender, SelectionChangedEventArgs e)
        {
            if (ComboBoxResultTextBlock == null) return;

            var combo = (ComboBox)sender;
            var item = (ComboBoxItem)combo.SelectedItem;
            ComboBoxResultTextBlock.Text = item.Content.ToString();

        }

        private void buttonPagar_Click(object sender, RoutedEventArgs e)
        {
            textBoxPago.Text = textBoxMonto. Text + ComboBoxResultTextBlock.Text;
        }
        
        private void textBoxPago_TextChanged(object sender, TextChangedEventArgs e)
        {

        }

        private void comboBox1_SelectionChanged(object sender, SelectionChangedEventArgs e)
        {

        }
    }
}
